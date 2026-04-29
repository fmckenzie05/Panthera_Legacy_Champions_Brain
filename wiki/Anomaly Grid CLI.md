---
type: product
tags:
  - product
  - cli
  - rust
  - defensive
  - sibling-product
entity: Intellusia Studios
updated: 2026-04-28
architecture-status: complete
implementation-progress: "E1 stories 1.1 + 1.2 + 1.3 + 1.4 of 10 (workspace + canonical Event + TelemetryAdapter trait + Zeek + syslog/journald)"
---
# Anomaly Grid CLI

Sibling product to [[Anomalie Grid]] — an AI-native, defensive network observation CLI for the **solo security operator**. Single Rust binary (`ag`), local-first, no daemon, no SaaS. Operator types plain-English questions about their own network and gets back tactical answers grounded in live telemetry from existing defensive sensors (Zeek, Suricata, Wazuh, syslog, journald). Every answer cites receipts: data source, time window, query plan, confidence.

## Summary

Where Anomalie Grid is the multi-tenant SaaS platform for MSSPs and internal security teams, Anomaly Grid CLI is the **solo-operator wedge**. It targets indie pentesters, fractional SOCs, and homelab defenders — operators who are sharp enough to run real sensor stacks but too time-pressured to live inside a SIEM. The product is **greenfield Rust**, separate repo (`anomaly-grid-cli`), with its own PRD, 7-epic breakdown, and competitor research (against Guardian-CLI). Adjacent FastAPI backend and Next.js dashboard from the main repo are explicitly out of scope for v1; CLI may consume them as optional enrichment later.

## Key Points

- One-liner positioning: "A solo defender opens a terminal at 2:47am, types a plain-English question about their network, and gets back a tactical answer with receipts. Single Rust binary, no SaaS, no install ceremony." (source: raw/anomaly-grid-cli-PRD.md / vision.oneLiner)
- Three load-bearing differentiators: (1) **defensive** posture in an AI-tool category that's otherwise offensive, (2) **plain-English-with-receipts** — every prose query compiles to a deterministic flag-form query the operator can read, edit, and trust, (3) **single-binary local-first** — no daemon, no SaaS, no Python venv, no LangChain. (source: raw/anomaly-grid-cli-PRD.md / What Makes This Special)
- Top-level binary: `ag`. v1 commands: `ag init`, `ag ask "<question>"`, `ag events [flags]`, `ag actors [flags]`, `ag examples`, `ag config`, `ag scope [add|remove|list]`, `ag adapters`. (source: raw/anomaly-grid-cli-PRD.md / Command Structure)
- Global flags: `--why` (show query plan), `--json`, `--no-llm` (force flag-form path), `--config <path>`, `--scope <name>`, `--receipts <terse|full|none>`, `-v`/`-vv`, `--version`. (source: raw/anomaly-grid-cli-PRD.md / Command Structure)
- v1 telemetry adapters: Zeek (`conn.log`, `dns.log`, `ssl.log`, `http.log`, TSV + JSON) and journald + syslog. Suricata is Phase 2 (Growth). Wazuh is Phase 3 (Vision). (source: raw/anomaly-grid-cli-PRD.md / Telemetry Tier + Phases)
- v1 LLM provider: Anthropic Claude only. Multi-provider abstraction (OpenAI, Gemini, local Ollama) is Growth. (source: raw/anomaly-grid-cli-PRD.md / Phase 2)
- Crate layout (Cargo workspace): `ag-core` (engine), `ag-adapters` (telemetry implementations), `ag-cli` (binary + flag parsing). `tokio` async, `reqwest` + `rustls` HTTP, `tracing` logging. Adapter trait: `name()`, `supported_versions()`, `query(predicate, time_window) -> Stream<Event>`, `schema()`. (source: raw/anomaly-grid-cli-PRD.md / Implementation Considerations)
- v1 OS targets: macOS arm64 + x86_64; Linux x86_64-gnu + x86_64-musl + arm64-gnu. Windows is v2. (source: raw/anomaly-grid-cli-PRD.md / NFR16)
- Performance NFRs: p95 English-query latency ≤ 8s; flag-form ≤ 1s; cold start ≤ 200ms; adapter throughput ≥ 50k events/sec; LLM cost ≤ $0.05/query with configurable per-session cap. (source: raw/anomaly-grid-cli-PRD.md / NFR1-6)
- Stable JSON schema in v1: `{schema_version, query: {english, flag_form, executed_at}, answer: {summary, confidence}, receipts: [...], metadata}`. Schema-version bump required for breaking changes. (source: raw/anomaly-grid-cli-PRD.md / Stable JSON schema)
- Exit codes (sysexits.h-aligned): 0 success, 1 query error, 2 no data, 3 LLM-translation failure, 4 LLM provider unreachable, 5 adapter/telemetry error. (source: raw/anomaly-grid-cli-PRD.md / Scripting Support)
- Privacy/security non-negotiables: API keys file mode `0600`; allow-list redactor before LLM (CI gate); structured-block delimiters around telemetry (prompt-injection mitigation); TLS for all outbound; signed releases (minisign or cosign). (source: raw/anomaly-grid-cli-PRD.md / Domain-Specific Requirements + NFR7-12)
- 7 MVP epics: E1 Local Telemetry Query Engine with Receipts → E2 Plain-English Query Layer → E3 Onboarding/Config/Cross-Platform Install → E4 Safe Operation on Engagements (Scope/Authorization/Audit) → E5 Scripting & Integration Surface → E6 Privacy/Security/Reliability Hardening → E7 Contributor/Adapter Extension Surface. Build order is sequential E1 → E2 first; E3–E7 can parallelize after. (source: raw/anomaly-grid-cli-EPICS.md / Epic List + Suggested Build Order)
- Success metrics (12 months): 1,000+ GitHub stars, 100+ weekly active users, 5+ "found a real thing" community stories, 3+ third-party adapters. **Intellusia self-use floor: tool runs on every paid client engagement within 6 months** — that's the N=1 dogfood guarantee. (source: raw/anomaly-grid-cli-PRD.md / Success Criteria)
- Test discipline: deterministic-shell unit tests at 100% in CI; LLM eval suite at ≥85% answer correctness on a curated fixture set, threshold blocks releases that regress. (source: raw/anomaly-grid-cli-PRD.md / Test gates + NFR29)
- Distribution model: open-source-first; no v1 revenue. Studios services or hosted CLI is a v2 conversation. Tool retains positioning value for Studios services even if pure-OSS adoption is slow. (source: raw/anomaly-grid-cli-PRD.md / Business Success + Risk Mitigation)
- Competitor analysis target: Guardian-CLI (Python LangChain-based, **offensive** posture, workflow-flag UX, 19 external pentest tools). Anomaly Grid CLI is the inverse on every axis: defensive, plain-English-primary, single Rust binary, sits-on-top-of-existing-sensors. (source: raw/anomaly-grid-cli-COMPETITOR_GUARDIAN.md)
- Author: Fred. PRD dated 2026-04-22. **Architecture doc completed 2026-04-28** — full 8-step BMad architecture workflow run end-to-end. Binds all 42 FRs / 29 NFRs to specific files and CI gates. Locks 4-crate workspace (`ag-core` / `ag-adapters` / `ag-cli` / `ag-eval`), workspace dependency catalog (tokio 1.x, clap 4.x, reqwest 0.12 with rustls, thiserror 2.x, tracing 0.1, sled 0.34 for translation cache, secrecy 0.10, ipnet 2.x, blake3 1.x), 5 CI gates (deterministic-shell, eval ≥85%, redactor coverage tracer, prompt-injection ≥95% block, JSON schema snapshot), and non-bypassable security seams (single redactor site, single prompt-builder, single scope enforcer). (source: _bmad-output/planning-artifacts/architecture.md in repos/anomaly-grid-cli)
- Architectural decision: v1 introduces a 4th crate `ag-eval` (alongside the PRD-specified ag-core / ag-adapters / ag-cli) so the eval suite is contributor-runnable from day one rather than maintainer-internal. Aligns Story 7.3 with E1 timing instead of deferring to Growth.
- Architectural decision: translation cache uses `sled` at v1 (pure-Rust embedded KV, content-addressed by `(blake3(query), blake3(telemetry_signature), model_id)`). `rusqlite` is the documented fallback if sled stability becomes a concern at v1.0 release candidate.
- Architectural decision: outbound HTTP uses `reqwest` directly against the Anthropic Messages API rather than a community SDK — keeps the dependency surface small and gives full control over the tool-use schema, which is the load-bearing English-to-flag-form contract.
- **Implementation status (2026-04-29):** Stories 1.1 + 1.2 + 1.3 + 1.4 landed. Cargo workspace builds clean (Rust 1.95 stable), `ag --version` ships the required fields, release binary is 631 KB stripped. Canonical `Event` schema and `TelemetryAdapter` trait shipped. **Zeek adapter** parses `conn.log` / `dns.log` / `ssl.log` / `http.log` in TSV and JSON. **Syslog adapter** parses BSD-format text logs (`/var/log/syslog`, `/var/log/auth.log`) with manual timestamp parser (avoids chrono format-string bugs on space-padded days). **Journald adapter** wired behind `journald` Cargo feature — off by default so dev container builds don't need libsystemd-dev; yields `AdapterError::Unavailable` when feature off so engine continues per NFR18. 48 tests + 1 doctest passing workspace-wide. CI: fmt + strict clippy (`-D unwrap_used -D expect_used`) + test all green. GitHub: pushed to `fmckenzie05/anomaly-grid-cli` and `fmckenzie05/intellusia-knowledge-base` on `main`. Next: Story 1.5 (`ag events` flag-form query — engine integration).
- Implementation note: workspace ships a 4th crate `ag-eval` (in addition to PRD's ag-core / ag-adapters / ag-cli) so the eval-suite harness is contributor-runnable from day one rather than maintainer-internal — aligns Story 7.3 timing with E1.
- Implementation note: `Protocol` enum has manual `Serialize`/`Deserialize` so it round-trips as a flat lowercase string (`"tls"`) including the open-ended `Other(String)` variant (`"quic"` → `Protocol::Other("quic".to_string())`). Adapter authors get type-safe matching on common protocols without losing rare ones.
- Implementation note: `RawLineRef` is a tagged enum (`{"kind":"file"|"journal", ...}`) so receipts can cite either line-numbered files (Zeek, syslog) or journald cursors with one type. Stable across reboots (cursors) and across runs (line numbers don't shift on append-only logs).

## Recall Questions

- **Q:** What language and binary distribution does Anomaly Grid CLI ship as? **A:** A single Rust binary called `ag`. No daemon, no SaaS, no Python venv. (source: raw/anomaly-grid-cli-PRD.md / vision.oneLiner)
- **Q:** What is the "plain-English-with-receipts" pattern? **A:** Every English query compiles down to a deterministic flag-form query the operator can read via `--why`, edit, re-run, and trust — the English is a UX layer over a deterministic engine, not a black box. (source: raw/anomaly-grid-cli-PRD.md / Innovation §1)
- **Q:** Which two telemetry adapters ship in v1? **A:** Zeek (conn/dns/ssl/http logs in TSV + JSON) and journald + syslog. (source: raw/anomaly-grid-cli-PRD.md / MVP Feature Set)
- **Q:** Which LLM provider does v1 ship against, and what is the v1 lock-in justification? **A:** Anthropic Claude only — accepted lock-in to ship faster; provider abstraction is the first work item in Phase 2. (source: raw/anomaly-grid-cli-PRD.md / Risk Mitigation)
- **Q:** Which exit code signals "LLM provider unreachable"? **A:** Exit code 4 — distinguishes "LLM down" from "query failed" so cron pipelines that use `--no-llm` can survive provider outages. (source: raw/anomaly-grid-cli-PRD.md / Scripting Support + FR40)
- **Q:** What is the Studios self-use success floor? **A:** Tool runs on every paid client engagement within 6 months — guarantees N=1 dogfood and positioning value even if external OSS adoption is slow. (source: raw/anomaly-grid-cli-PRD.md / Business Success)
- **Q:** Who is the canonical competitor and on what axes is Anomaly Grid CLI the inverse? **A:** Guardian-CLI — they are offensive (point at a target), workflow-flag UX, Python + 19 external tools. We are defensive (watch own infra), plain-English primary, Rust single-binary, sits-on-top-of-existing-sensors. (source: raw/anomaly-grid-cli-COMPETITOR_GUARDIAN.md)

## Related

- [[Anomalie Grid]]
- [[Sentinel Swarm]]
- [[Telemetry Ingest API]]
- [[Actor Profiling]]
- [[MITRE Coverage]]
- [[Intellusia Studios]]

## Sources

- raw/anomaly-grid-cli-PRD.md
- raw/anomaly-grid-cli-EPICS.md
- raw/anomaly-grid-cli-ARCHITECTURE.md
- raw/anomaly-grid-cli-COMPETITOR_GUARDIAN.md
- repos/anomaly-grid-cli/_bmad-output/planning-artifacts/architecture.md (live, completed 2026-04-28)
