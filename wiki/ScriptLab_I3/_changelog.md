---
title: Wiki Changelog
type: changelog
---

# Wiki Changelog

Append-only log of every ingest and structural change to the wiki.

---

## 2026-06-05 — WORLDVIEW updated: Law of Six added as product design belief

**Change:** Added "On networks and distribution (Law of Six)" as a new belief section in WORLDVIEW.md. Six degrees of separation encoded as an explicit application design principle.

**Core beliefs added:**
- The world is 6 hops wide — the network is smaller than it feels; design for it
- A relationship requires two bidirectional nodes; 6 is the depth at which the reachable universe closes
- Build the path, not just the destination — the path is the product
- For content creators, the 6-degree graph already exists — the product makes it visible and actionable
- Trust but verify = trace the path; mutual nodes are vouchers; path depth is credibility signal
- Crossover with Anomalie Grid: adversary lateral movement is the same graph traversal problem

**Application design implication encoded:**
1. Show the path, not just the endpoint
2. Require bidirectionality to gate trust
3. Use shared-path depth as a credibility signal
4. Let users strengthen their own nodes so others' paths through them gain value

**Files updated:**
- `wiki/WORLDVIEW.md` — new section added; 4 new recall questions added
- `wiki/_flashcards.md` — 5 new cards added under `[[WORLDVIEW]] — Law of Six`

---

## 2026-06-05 — MEMORY.md updated: Anomaly Grid CLI + Kofi Cyber Synthesis added as named nodes

**Change:** Full session re-read. MEMORY.md was missing both new nodes added yesterday. Updated to reflect current vault state.

**Files updated:**
- `MEMORY.md` — added Node #10 (Anomaly Grid CLI) and Node #11 (Kofi Cyber Synthesis) to primary company node map; updated Node relationships section; updated Practical company graph quick recall; updated Current concise memory; removed stale "test" artifact

**Raw/ status:** 13 kofi-*.md files present. All already ingested into `wiki/Kofi Cyber Synthesis.md`. No new uningest files.

---

## 2026-06-04 — Graph alignment: Kofi Cyber Synthesis + Anomaly Grid CLI wired in

**Change:** Added Kofi Cyber Synthesis and Anomaly Grid CLI to the graph and properly connected them to Anomalie Grid.

**Files updated:**
- `wiki/Kofi Cyber Synthesis.md` — `type` updated to `knowledge`; tags updated to `knowledge, intelligence, cyber, soc, anomalie-grid`; broken `[[Kofi MOC]]` wikilink removed
- `ScriptLab8_I3.md` — Added `[[Anomaly Grid CLI]]` and `[[Kofi Cyber Synthesis]]` to Anomalie Grid section + hierarchy tree + Relationship Edges section
- `wiki/Anomalie Grid.md` — Added structured component/sibling/knowledge sections with links to all component nodes, Anomaly Grid CLI, and Kofi Cyber Synthesis
- `GRAPH_FILTER_GUIDE.md` — Added Kofi + CLI to product architecture view; added `rel-intelligence` Kofi row to Anomalie Grid color table
- `wiki/_index.md` — Added `Rel - Anomalie Grid to Kofi Cyber Synthesis` entry

**New file:**
- `wiki/Rel - Anomalie Grid to Kofi Cyber Synthesis.md` — cyan / rel-intelligence edge connecting knowledge layer to product

**Result:** Kofi Cyber Synthesis is now a proper named node in the graph, linked to Anomalie Grid via a `rel-intelligence` relationship edge. Anomaly Grid CLI is visible in the graph hub as the sibling product.

---

## 2026-06-04 — Post-removal stale reference sweep

**Change:** Cleaned up all remaining stale references left after OpenClaw removal and INTELLUSIA_GRAPH rename.

**Files updated:**
- `CLAUDE.md` — fixed title, `INTELLUSIA_GRAPH.md` → `ScriptLab8_I3.md` (2 occurrences), `[[INTELLUSIA_GRAPH]]` → `[[ScriptLab8_I3]]`, "OpenClaw surfaces" → "ScriptLabs studio connectors"
- `GRAPH_FILTER_GUIDE.md` — 3× `INTELLUSIA_GRAPH` → `ScriptLab8_I3`
- `HOME.md` — recall question updated to reference `ScriptLab8_I3`
- `wiki/ScriptLab_I3.md` — converted from raw source doc to proper redirect stub pointing to `ScriptLab_I3/_index`
- `wiki/_flashcards.md` — `[[ScriptLab_I3/OpenClaw_Stack]]` section renamed to `[[ScriptLab_I3/Studio_Workflow]]`; source citations updated
- `wiki/FIRST_POPULATION_NOTE.md`, `EXAMPLE_IDEA_NOTE.md`, `EXAMPLE_PROJECT_UPDATE.md`, `EXAMPLE_MEETING_NOTE.md`, `TEMPLATE_VERIFICATION_NOTE.md` — `[[OpenClaw]]` wikilinks replaced with `[[ScriptLab_I3/_index]]`

**Result:** Zero `OpenClaw` or `INTELLUSIA_GRAPH` references in any live content file. Only historical entries in `_changelog.md` and reference-only `Templates/` folder remain.

---

## 2026-06-04 — OpenClaw fully removed; soul and workflow remapped

**Change:** Deleted OpenClaw as a concept entirely. Remapped all references to either ScriptLabs Studios (entity owner) or the ScriptLab_I3 soul/workflow cluster (functional layer).

**Deleted files (12):**
- `wiki/OpenClaw.md`
- `wiki/OPENCLAW_OPERATIONS_AND_CONNECTOR_STRATEGY.md`
- `wiki/Rel - Intellusia to OpenClaw.md`
- `wiki/Rel - ScriptLabs to OpenClaw.md`
- `wiki/Rel - OpenClaw to Claude.md`
- `wiki/Rel - OpenClaw to Discord.md`
- `wiki/Rel - OpenClaw to Hostinger VPS.md`
- `wiki/Rel - OpenClaw to OpenRouter.md`
- `wiki/Rel - OpenClaw to Postman MCP.md`
- `wiki/Rel - OpenClaw to Telegram.md`
- `wiki/Rel - OpenClaw to WhatsApp.md`
- `wiki/Rel - OpenClaw to YouTube.md`

**Renamed:** `wiki/ScriptLab_I3/OpenClaw_Stack.md` → `wiki/ScriptLab_I3/Studio_Workflow.md` (rewritten, OpenClaw branding removed)

**What remained (soul + workflow):**
- `wiki/ScriptLab_I3/LLM_Soul.md` — Hermes identity, system prompt, priorities
- `wiki/ScriptLab_I3/Behavioral_Rules.md` — LLM behavioral contract
- `wiki/ScriptLab_I3/Studio_Workflow.md` — agentic delivery pipeline (was OpenClaw_Stack)
- `wiki/ScriptLab_I3/Studio_Operating_Context.md` — studio operating model

**Text replaced across all live files:** `[[OpenClaw]]` → `[[ScripLabStudio8]]` or `[[ScriptLab_I3/Studio_Workflow]]` depending on context. All bare "OpenClaw" prose replaced with "ScriptLabs studio stack" / "ScriptLabs automation". Zero remaining hits in live content files.

**Files touched:** 20+ (connector stubs, structural files, relationship files, soul cluster, graph hub, MEMORY, HOME, GRAPH_FILTER_GUIDE, _index, OPERATOR_PROFILE, DECISION_PRINCIPLES, WORLDVIEW, OPERATING_RHYTHM, AI_DESIGN_PATTERNS, GOVERNMENT_CONTRACTING_PIPELINE_STRATEGY)

**Pages deleted:** 12 | **Pages renamed:** 1 | **Pages rewritten:** 15+

---

## 2026-06-04 — Hierarchy restructure: Intellusia I3 → ScriptLabs → OpenClaw

**Change:** Repurposed all infrastructure/ops references from Intellusia to ScriptLabs Studios. Established three-layer hierarchy with Intellusia I3 as head, ScriptLabs Studios as revenue face, OpenClaw as the ops layer underneath ScriptLabs.

**Entity field changes (all connector/infrastructure nodes):**

| File | Before | After |
|---|---|---|
| `OpenClaw.md` | `entity: Intellusia Studios` | `entity: ScriptLabs Studios` |
| `Claude.md` | `entity: OpenClaw` | `entity: ScriptLabs Studios` |
| `Discord.md` | `entity: OpenClaw` | `entity: ScriptLabs Studios` |
| `Telegram.md` | `entity: OpenClaw` | `entity: ScriptLabs Studios` |
| `WhatsApp.md` | `entity: OpenClaw` | `entity: ScriptLabs Studios` |
| `YouTube.md` | `entity: OpenClaw` | `entity: ScriptLabs Studios` |
| `Hostinger VPS.md` | `entity: OpenClaw` | `entity: ScriptLabs Studios` |
| `OpenRouter.md` | `entity: OpenClaw` | `entity: ScriptLabs Studios` |
| `Postman MCP.md` | `entity: OpenClaw` | `entity: ScriptLabs Studios` |
| `OPENCLAW_OPERATIONS_AND_CONNECTOR_STRATEGY.md` | `entity: Intellusia Studios` | `entity: ScriptLabs Studios` |
| All `Rel - OpenClaw to *.md` | `entity: OpenClaw` | `entity: ScriptLabs Studios` |
| All `ScriptLab_I3/*.md` | `entity: Intellusia Studios / ScriptLab_I3` | `entity: ScriptLabs Studios` |

**New file:** `wiki/Rel - ScriptLabs to OpenClaw.md` — direct operational edge (orange / rel-operations)

**Updated files:** `Rel - Intellusia to OpenClaw.md`, `ScriptLab8_I3.md` (hierarchy diagram), `MEMORY.md` (hierarchy section → three-layer model), `wiki/_index.md`

**Pages created:** 1
**Pages updated:** 18
**Flashcards added:** 0

---

## 2026-06-04 — ScripLabStudio8 knowledge base rebuilt from source repo

**Source:** `Scriptstudio8/ScriptLabs_Site` (private GitHub repo, cloned to `S:\hostinger_vps_openclaw_2_hermes_i3_socialmarketing\ScriptLabs_Site`)
**Files read:** `app/page.tsx`, `app/about/page.tsx`, `app/services/page.tsx`, `app/layout.tsx`, `package.json`, `ScriptLabs_Studios/prd.md`

**Key corrections vs. earlier scrape-based entry:**

| Field | Scraped (wrong) | Source (correct) |
|---|---|---|
| Founded | 2019 | **2018** |
| CEO | "Alex Chen" (placeholder) | **Honorine Ndom Ndzah** |
| CIO | "Sarah Johnson" (placeholder) | **Fernando A McKenzie** |
| Tagline | (generic) | **"Creating innovative solutions out of thin air"** |
| Service pillars | 5 | **6** (Support & Maintenance added) |
| Pricing | none listed | **$5K–$15K+ per service, $200/hr consulting** |
| Tech stack | generic | **Next.js 15.4.5 / React 19 / Framer Motion / MUI / Tailwind** |

**What landed:**
- `wiki/ScripLabStudio8.md` — full rewrite with source-verified data; real founders, real pricing, full site structure, brand colors, website tech stack, PRD targets
- `wiki/_flashcards.md` — ScripLabStudio8 deck replaced (5 stale cards out, 7 source-verified cards in)

**Pages created:** 0
**Pages updated:** 1 (ScripLabStudio8)
**Flashcards replaced:** 5 stale → 7 verified
**Contradictions resolved:** founding year, all team names, service count, pricing

---

## 2026-06-04 — Two-tier brand structure wired into graph

**Change:** Encoded Intellusia Studios (mother company) → ScriptLab_I3 (client-facing brand) relationship across the vault.

**What changed:**
- `ScriptLab8_I3.md` (vault root / graph hub) — full rewrite; now leads with two-tier entity structure diagram, Tier 1 (Intellusia) and Tier 2 (ScriptLab_I3) sections, correct relationship edges including new `Rel - Intellusia to ScriptLab_I3`
- `wiki/Rel - Intellusia to ScriptLab_I3.md` — new relationship edge node (gold / `rel-brand`); defines parent → client-face meaning and brand separation logic
- `wiki/Intellusia Studios.md` — updated to explicitly mark Intellusia as mother company; added brand structure table showing ScriptLab_I3 as the client face
- `wiki/ScriptLab_I3/_index.md` — added Brand Position block at top; clarifies ScriptLab_I3 is the public face, Intellusia is the holder
- `MEMORY.md` — added Brand Structure section (two-tier table) above Company Snapshot; includes messaging rule (Anomalie Grid / GovCon under Intellusia; web/mobile/Web3 delivery under ScriptLab_I3)
- `GRAPH_FILTER_GUIDE.md` — added gold `rel-brand` row to Intellusia outbound relationship table; updated Clean Executive Map to include ScriptLab_I3 node
- `HOME.md` — Core Company Map section replaced with table showing Intellusia (mother), ScriptLab_I3 (client face), Anomalie Grid, OpenClaw
- `wiki/_index.md` — added `Rel - Intellusia to ScriptLab_I3` to Relationship Edges section

**Pages created:** 1 (`Rel - Intellusia to ScriptLab_I3`)
**Pages updated:** 7
**Flashcards added:** 0
**Contradictions:** None

---

## 2026-06-04 — ScriptLab_I3 LLM soul cluster built

**Source:** wiki/ScriptLab_I3.md (primary), wiki/MEMORY.md, wiki/OPERATOR_PROFILE.md, wiki/OpenClaw.md + connector nodes

**What landed:**
- New folder: `wiki/ScriptLab_I3/` — LLM soul cluster for the Intellusia Agentic Studio / OpenClaw deployment
- `wiki/ScriptLab_I3/_index.md` — Hub/MOC for the cluster; maps all sub-files and upstream sources
- `wiki/ScriptLab_I3/LLM_Soul.md` — Core soul file: Hermes identity, 5 optimization priorities, personality/voice rules, system prompt template, self-duplication contract
- `wiki/ScriptLab_I3/Studio_Operating_Context.md` — Studio operating model (solo + creator network + agentic layer), Web3 ramp phases, delivery stack, who we sell to, near-term actions (derived from ScriptLab_I3.md)
- `wiki/ScriptLab_I3/OpenClaw_Stack.md` — Full connector map: Hermes, GHL + GHL MCP, Claude Code, OpenRouter, Discord/Telegram/WhatsApp, Hostinger VPS, Postman MCP; includes agentic pipeline flow diagram
- `wiki/ScriptLab_I3/Behavioral_Rules.md` — Hard behavioral contract: always/never rules, messaging guardrails (preferred/avoided framing), delegation boundaries, 5-point quality test, conflict resolution order
- Added 13 new flashcards across 4 sub-pages to `wiki/_flashcards.md`
- Added `ScriptLab_I3 — LLM Soul Cluster` section to `wiki/_index.md`

**Pages created:** 5 (inside wiki/ScriptLab_I3/)
**Pages updated:** 0
**Flashcards added:** 13
**Contradictions:** None

---

## 2026-06-04 — ScripLabStudio8 node created

**Source:** `scriptstudio8.com` (homepage, /services, /about, /portfolio)

**What landed:**
- New wiki page: [[ScripLabStudio8]] — external company node for ScriptLab Studio 8, an AI-powered development studio operating across mobile, web, and Web3 domains.
- Covers: 5 service pillars (Web Dev, Mobile Dev, Web3/Blockchain, AI SaaS, Consulting), full tech stack (React/Next.js/Flutter/Solidity/TensorFlow/LangChain), portfolio highlights (FinanceAI Pro, HealthTrack Mobile, DeFi Exchange, E-Commerce Revolution, TeamCollab SaaS, SmartCity IoT), company timeline (2019–2024), leadership team, and GTM model.
- Added recall deck (5 questions) to `wiki/_flashcards.md`.
- Added section **External Companies & Reference Nodes** to `wiki/_index.md`.

**Caution:** Some site details (phone number, team names, client stats) show signs of being placeholder/template content. Flagged with ⚠️ note in the wiki page.

**Pages created:** 1 (ScripLabStudio8)
**Pages updated:** 0
**Flashcards added:** 5
**Contradictions:** None

---

## 2026-04-30 — Kofi cyber notes ingested

**Source:** `share_internal_kofi/Obsinthe/` (Kofi's TryHackMe-style cybersecurity notes).

**What landed:**
- 13 notes copied into `raw/` with `kofi-` prefix: anomaly-grid-architecture (Kofi's Matrix-themed arch spec), mitre, cyber-kill-chain, diamond-model, pyramid-of-pain, unified-kill-chain, soc-fundamentals, intro-to-siem, intro-to-edr, yara, sysmon, threat-intel-tools, intro-to-cti.
- New synthesis page: [[Kofi Cyber Synthesis]] — maps Kofi's Matrix codenames (Oracle, Architect, Nebuchadnezzar, Zion, Construct, Sentinel Swarm, Red Pill) to existing I3 wiki nodes; positions Kofi's frameworks (MITRE, Diamond, Kill Chain, Pyramid of Pain) as analyst-buyer language for [[Anomalie Grid]].
- Vault-root [[Kofi MOC]] created for navigation; cross-link added in Kofi's `Anomaly Grid.md` → [[Anomalie Grid]]; `Home.md` Quick Nav updated.

**Rule:** Kofi's source folder is read-only. To pull in additional notes, copy into `raw/` with `kofi-` prefix and update the synthesis page — do not edit Kofi's originals.

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

