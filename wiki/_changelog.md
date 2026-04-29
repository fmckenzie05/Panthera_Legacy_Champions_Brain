---
title: Wiki Changelog
type: changelog
---

# Wiki Changelog

Append-only log of every ingest and structural change to the wiki.

---

## 2026-04-29 — Anomaly Grid CLI Story 1.4 (syslog + journald-stub) implemented

**Source:** `repos/anomaly-grid-cli/crates/ag-adapters/src/journald_syslog/`.

**What landed:**
- `SyslogAdapter` — full file-tail implementation for BSD-style syslog text files (`/var/log/syslog`, `/var/log/auth.log`, etc.). Parses `MMM DD HH:MM:SS HOSTNAME TAG[PID]: MESSAGE` format, handles single-digit days with double-space padding, and skips tag-internal colons (e.g. `pam_unix(sudo:auth)`). Manual timestamp parser sidesteps a chrono `%e`/`%d` format-string bug on space-padded vs zero-padded days.
- `JournaldAdapter` — feature-gated (`journald` Cargo feature, off by default). Constructible without the feature so config (Story 3.5) and `ag adapters` (Story 1.9) can reference it; `query()` yields a single `AdapterError::Unavailable` when the feature is off, so the engine continues with other adapters per NFR18. Real systemd-journal integration ships when `libsystemd-dev` is in the build environment.
- Both adapters use loopback (127.0.0.1) for `Event.src` / `Event.dst` since host-level log records have no real network endpoint, and `Protocol::Other("syslog")` / `Protocol::Other("journald")`. Tag, PID, and message land in `Event.fields`.
- `SyslogAdapter::new(paths, host, default_year)` — operator passes the year to anchor BSD-style timestamps that lack one; tests pass a fixed year, real deployments default to current year.

**Tests:** 7 unit tests on the parser (sshd line, sudo with no PID, systemd line, short-line rejection, malformed timestamp, double-space day, separator-finder bracket-skip), 8 integration tests on the adapter (end-to-end ingest, hostname fallback, tag/PID extraction, time-window filter, missing-path tolerance, supported_versions, raw_line_ref shape), 3 unit tests on the journald stub (Unavailable behavior, build-mode introspection, name/version stability).

**Cumulative state:** 48 tests pass workspace-wide (2 cli + 9 core + 37 adapters). `cargo build`, `cargo fmt --check`, `cargo clippy -D warnings -D unwrap_used -D expect_used` all clean.

**Why:** Story 1.5 (`ag events`) needs at least one always-available adapter to demonstrate engine integration; SyslogAdapter is that adapter for any host without a Zeek install. JournaldAdapter is wired now (rather than Phase 2) so `ag adapters` listing and config schema are stable from v1 day one.

---

## 2026-04-28 — Anomaly Grid CLI Story 1.3 (Zeek adapter) implemented

**Source:** `repos/anomaly-grid-cli/crates/ag-adapters/src/zeek/`.

**What landed:**
- `ZeekAdapter` reading `conn.log` / `dns.log` / `ssl.log` / `http.log` from a configured directory; auto-detects TSV vs JSON from the first non-empty line (`{` → JSON, else → TSV); `supported_versions()` returns `["4.x", "5.x"]` per Story 1.3 AC.
- TSV parser handles `#fields` header, skips other `#` metadata, validates column count, treats `-` / `(empty)` as unset, parses Unix-float timestamps to `DateTime<Utc>`.
- JSON parser uses `serde_json::Value` with key-by-key extraction (Zeek emits dotted keys like `"id.orig_h"` literally rather than nested objects).
- Per-record errors yield `Err` items into the stream rather than aborting the file (NFR18 partial-telemetry tolerance).
- Zeek's `host` HTTP-header field is renamed to `host_header` in `Event.fields` to disambiguate from `Event.host` (sensor hostname).
- Streaming via `async_stream::stream!` macro (added `async-stream` to workspace catalog) over `tokio::fs::File` + `BufReader::lines()` — lazy, no in-memory accumulation per architecture's "streaming, no whole-dataset buffer" rule.
- 11 unit tests + 9 integration tests pass; fixtures committed at `crates/ag-adapters/tests/fixtures/zeek/{tsv,json}/{conn,dns,ssl,http}.log`. TSV fixtures use real tab characters (verified with `cat -A`).

**Why:** Stories 1.5 (`ag events`) and 1.10 (determinism integration test) both need a working Zeek adapter to exercise the engine pipeline.

**Cumulative state:** 31 tests pass workspace-wide (2 cli + 9 core + 20 adapters). `cargo build --release`, `cargo fmt --check`, `cargo clippy -D warnings -D unwrap_used -D expect_used` all clean.

---

## 2026-04-28 — Anomaly Grid CLI Stories 1.1 + 1.2 implemented

**Source:** `repos/anomaly-grid-cli/crates/{ag-core,ag-adapters,ag-cli,ag-eval}/` (workspace artifacts).

**Stories landed:**
- **Story 1.1** — Cargo workspace bootstrap. 4 crates (`ag-core`, `ag-adapters`, `ag-cli`, `ag-eval`); `ag --version` prints version + build date + git short hash + adapter list. Release binary 631 KB stripped (≪ 50 MB target). CI workflow stubs (`fmt + strict clippy + test` wired; `release` / `bench` stubs point at owning stories). Workspace lints set warn for `clippy::unwrap_used` / `expect_used` / `panic`; CI escalates to deny.
- **Story 1.2** — Canonical `Event` schema in `ag-core::types` (timestamp, source_adapter, host, src/dst Endpoint, proto, severity, raw_line_ref, fields BTreeMap). `TelemetryAdapter` trait in `ag-adapters::trait_def` with `name()` / `supported_versions()` / `schema()` / `query()`; `EventStream` is `Pin<Box<dyn Stream<Item = Result<Event, AdapterError>> + Send>>` for object safety. Rustdoc worked example compiles as a doctest. 12 tests pass: serde round-trip (incl. IPv6), byte-stable JSON, Protocol flat-string serialization with `Other(String)` round-trip, RawLineRef tagged-enum round-trip, Severity ordering, TimeWindow inverted-range refusal, trait object safety, const Schema constructibility.

**Toolchain:** Rust 1.95.0 stable installed via rustup (minimal profile + clippy + rustfmt) on the openclaw container.

**Why:** Per Fred's instruction (2026-04-28) to update the vault per task completion, not just per architectural decision. Wiki page `Anomaly Grid CLI.md` reflects implementation progress so future agents can see what's shipped vs. designed.

**What this binds:** the canonical `Event` shape is now load-bearing — every adapter (Stories 1.3 Zeek, 1.4 journald) and the engine reason over it. JSON serialization is deliberately stable (BTreeMap-backed extras, Protocol/Severity flat strings) so that determinism (FR12, NFR19) holds. Future field additions are additive only.

---

## 2026-04-28 — Anomaly Grid CLI architecture completed

**Source:** `repos/anomaly-grid-cli/_bmad-output/planning-artifacts/architecture.md` (workspace artifact, not ingested into `raw/`).

**Pages updated:**
- `wiki/Anomaly Grid CLI.md` — replaced "architecture is a stub" line with a completed-architecture summary; added 3 key architectural decisions (4th crate `ag-eval`, sled for translation cache, direct reqwest vs community SDK); added live source pointer; added `architecture-status: complete` frontmatter.

**Why:** Per the workspace infra-sync rule (any infrastructure decision in a workspace repo updates the I3 vault), the architecture is shape-of-system information that downstream agents need. The stub note in the wiki was stale.

**What this binds:** 4-crate Cargo workspace, workspace dependency catalog (tokio/clap/reqwest+rustls/thiserror/tracing/sled/secrecy/ipnet/blake3), 5 CI gates, non-bypassable security seams (redactor, prompt-builder, scope enforcer). All 42 FRs and 29 NFRs map to specific files and gates.

---

## 2026-04-28 — Initial restructure into Karpathy schema

**Source:** None (no `raw/` documents ingested yet — this entry covers a structural conversion of the pre-existing flat vault).

**Pages created:**
- `wiki/_index.md`
- `wiki/_changelog.md`
- `wiki/_flashcards.md`

**Pages moved into `wiki/` (preserving git history via `git mv`):** ~60 files, including all entity, concept, and `Rel - *` notes plus the `Playbooks/` subfolder. See `_index.md` for full list.

**Pages updated:**
- `wiki/WORLDVIEW.md` — merged former `WORLDVIEW.md` (internal beliefs) + `WORLD_VIEW.md` (outward trends hub) into a single page with two parts. Cross-references inside the page were updated; recall questions added.

**Pages removed:**
- `WORLD_VIEW.md` — content folded into merged `wiki/WORLDVIEW.md`.

**Empty subfolders removed:** `ADRs/`, `Competitive/`, `Operations/`, `Samples/`, `Verticals/` (recreate inside `wiki/` as needed).

**Stayed at vault root:** `CLAUDE.md`, `MEMORY.md`, `LICENSE`, `HOME.md`, `INTELLUSIA_GRAPH.md`, `GRAPH_FILTER_GUIDE.md`, `Templates/`, `scripts/`, `.obsidian/`, `.claude/`.

**Flashcards added:** 5 root concepts seeded with 3–5 atomic recall questions each — `OPERATOR_PROFILE`, `WORLDVIEW`, `OpenClaw`, `Anomalie Grid`, plus the merged `WORLDVIEW` itself. `HOME.md` (vault entry, not in `wiki/`) also gets cards. See `_flashcards.md`.

**Contradictions surfaced:** None.

**Known gaps to resolve later:**
- Most pages have no `## Sources` section yet — claims will need `(inferred)` tags or backfilled citations once `raw/` source documents land.
- Most pages still lack the 3–5 recall questions required by the schema. Only 5 root pages were seeded in this pass.
- `Rel - Intellusia to World View.md` filename now points to a renamed concept (the merged `WORLDVIEW`) — consider renaming the rel note for clarity.
- `Templates/` is uppercase; `CLAUDE.md` was updated to match (Karpathy schema's lowercase `templates/` was relaxed).

---

## 2026-04-28 — Repo ingest: anomaly-grid + anomaly-grid-cli

**Sources ingested into `raw/`** (snapshot of repo state at 2026-04-28):

From `repos/anomaly-grid/`:
- `raw/anomaly-grid-README.md`
- `raw/anomaly-grid-SOUL.md`
- `raw/anomaly-grid-CODE_REVIEW.md` (1,061 lines, dated 2026-04-15, scored 4/10 overall)
- `raw/anomaly-grid-MORPHEUS_INFRA_SCHEMA.md` (the 7-layer architecture)
- `raw/anomaly-grid-api-main.py` (FastAPI backend, 493 lines, 15+ routes)
- `raw/anomaly-grid-supabase-001_schema.sql` (PostgreSQL schema, 293 lines, RLS via JWT claim)
- `raw/anomaly-grid-docker-compose.yml`
- `raw/anomaly-grid-dashboard-types.ts` (TS interfaces aligned to DB schema)
- `raw/anomaly-grid-PRD.md` (draft-v0, dated 2026-04-17)
- `raw/anomaly-grid-PRFAQ.md` (draft-v1, dated 2026-04-17)

From `repos/anomaly-grid-cli/`:
- `raw/anomaly-grid-cli-PRD.md` (700 lines, dated 2026-04-22, author: Fred)
- `raw/anomaly-grid-cli-EPICS.md` (1,086 lines, 7 MVP epics + ~60 stories)
- `raw/anomaly-grid-cli-ARCHITECTURE.md` (stub — only step-01-init completed)
- `raw/anomaly-grid-cli-COMPETITOR_GUARDIAN.md` (Guardian-CLI competitor research)

**Pages updated** (existing component pages rewritten with repo-grounded facts, citations, recall questions, and `## Sources` blocks):
- `wiki/Anomalie Grid.md` — full rewrite. Added build state, beachhead positioning, component graph, conflict block on honeynet framing.
- `wiki/Nebuchadnezzar.md` — Morpheus pipelines, Triton models, GPU sizing, mock-mode reality.
- `wiki/Sentinel Swarm.md` — Layer 1+2 components (Go agent, Zeek, PF_RING, mTLS), air-gap mode, edge GPU options.
- `wiki/The Construct.md` — added `> ⚠️ Conflict:` block: honeynet/decoy framing is **not** in current PRD/PRFAQ; treat as roadmap.
- `wiki/The Oracle.md` — flagged as architectural roadmap (no `/api/oracle/*` endpoints exist); pipeline-3 substrate noted.
- `wiki/Zion.md` — concrete framework versions, implemented routes, code-review critical issues (auth stub, Mission Control unprotected, false trust badges).
- `wiki/The Architect.md` — DB-substrate detail (platform_admins, tenant_summary view, RLS), tenant onboarding flow.
- `wiki/Red Pill Onboarding.md` — distinguishes brand layer from technical onboarding flow; called out the 1–2 week DFP baseline expectation.

**Pages created** (new wiki pages with full Karpathy structure):
- `wiki/Anomaly Grid CLI.md` — sibling product, Rust single-binary, defensive-CLI, plain-English-with-receipts
- `wiki/Morpheus Infra Schema.md` — the 7-layer architecture as a first-class wiki page
- `wiki/Mission Control.md` — multi-tenant operator view (the MSSP beachhead surface)
- `wiki/Telemetry Ingest API.md` — `POST /api/telemetry/ingest` contract + auth gap
- `wiki/Actor Profiling.md` — FR-4 capability, mocked actors, Morpheus pipeline-3 path
- `wiki/Passive Fingerprinting.md` — `device_fingerprints` table, Triton Device Classifier, three in-repo tools
- `wiki/MITRE Coverage.md` — `/api/mitre/coverage` aggregate + per-event tactic/technique tagging
- `wiki/Anomaly Grid Build Status.md` — implemented-vs-designed delta, top-5 v1 priorities
- `wiki/Anomaly Grid PRFAQ.md` — positioning + the four "do not claim" messaging guardrails

**Relationship notes added:**
- `wiki/Rel - Anomalie Grid to Anomaly Grid CLI.md`
- `wiki/Rel - Intellusia to Anomaly Grid CLI.md`
- `wiki/Rel - Nebuchadnezzar to Morpheus Infra Schema.md`
- `wiki/Rel - Anomalie Grid to Mission Control.md`
- `wiki/Rel - Sentinel Swarm to Telemetry Ingest API.md`

**Meta files updated:**
- `wiki/_index.md` — added new pages under Company / Brand Surface and a new Capabilities section; added 5 new relationship rows
- `wiki/_flashcards.md` — appended ~36 new recall Q&A across the new and updated pages
- `MEMORY.md` (vault root) — appended a 2026-04-28 repo-grounded delta with implemented endpoints, sibling product, and build status

**Contradictions surfaced:**
- ⚠️ The vault's prior framing of [[The Construct]] as "one of the strongest differentiators" conflicts with the current PRD/PRFAQ which leads with passive telemetry, anomaly scoring, fingerprinting, and actor-centric investigation — honeynet/decoy is not a current differentiator. Marked in `wiki/The Construct.md`.
- ⚠️ Code review identifies several issues that contradict the architecture's defense-in-depth stance: no auth on the dashboard, `/mission-control` exposes all-tenant data without role check, false SOC 2 / FedRAMP badges. Captured in `wiki/Zion.md`, `wiki/Mission Control.md`, `wiki/Anomaly Grid Build Status.md`.
- ⚠️ The infra schema specifies mTLS + per-tenant X.509 cert binding at the relay layer, but the actual `POST /api/telemetry/ingest` endpoint accepts the `tenant_id` from the request body without verification. Captured in `wiki/Telemetry Ingest API.md`.

**Stayed at vault root:** `MEMORY.md` (updated, not moved), `CLAUDE.md`, `HOME.md`, `INTELLUSIA_GRAPH.md`, `GRAPH_FILTER_GUIDE.md`, `LICENSE`.

**Known gaps after this pass:**
- Architecture document for Anomaly Grid CLI is still a stub (only step-01-init completed) — no technical-design-level content available yet.
- The dashboard UI pages were summarized via the code review and a partial source read; if exact widget inventories matter, do a targeted re-ingest of the `dashboard/src/app/dashboard/*` files.
- Older wiki pages (e.g., `Buyer Personas`, `Tenant Model`, `Onboarding Path`, `Client Journey`) were not touched in this pass even though the repo's PRD/PRFAQ has fresh content that could refine them — flagged for a follow-up ingest.

