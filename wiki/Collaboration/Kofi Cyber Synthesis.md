---
title: Kofi Cyber Synthesis
type: knowledge
tags:
  - knowledge
  - intelligence
  - cyber
  - soc
  - anomalie-grid
entity: Intellusia Studios
updated: 2026-06-04
---

# Kofi Cyber Synthesis

Synthesis of cyber/SOC fundamentals contributed by **Kofi**. Sources are in `raw/kofi-*.md` — copies of Kofi's `Obsinthe/` notes, prefixed for sortability.

## Why this matters for [[Anomalie Grid]]

Kofi's notes give us the analyst-side language of the buyer. Anomalie Grid's primary user is a SOC L1/L2 analyst or detection engineer — these notes describe exactly the workflow we plug into: alert triage, kill-chain framing, MITRE mapping, SIEM/EDR integration, threat intel pivots, YARA/Sysmon detection content.

## Architecture cross-reference (Kofi's Matrix spec → I3)

`raw/kofi-anomaly-grid-architecture.md` is Kofi's Matrix-themed Anomaly Grid architecture write-up. Codename map vs current I3 wiki:

| Kofi codename | I3 wiki node | Status |
|---|---|---|
| The Oracle | [[The Oracle]] | Already in vault — agentic reasoning over inference |
| The Architect | [[The Architect]] | Already in vault — admin/control plane |
| Nebuchadnezzar | [[Nebuchadnezzar]] | Already in vault — Morpheus + Triton |
| Zion | [[Zion]] | Already in vault — tenant Next.js portal |
| The Construct | [[The Construct]] | Already in vault — honeynet (roadmap, not beachhead) |
| Sentinel Swarm | [[Sentinel Swarm]] | Already in vault — Layer 1 collectors |
| The Red Pill | *(no node)* | Tenant onboarding flow — candidate for new wiki node if Red Pill becomes a named tier |

Tier names from Kofi's note (Red Pill / Operator / The One) are **marketing/packaging**, not in I3 PRD. Compare with I3's PRD beachhead in [[Anomalie Grid]]: boutique MSSPs, internal multi-site security teams, defense-adjacent operators.

## Frameworks Kofi covers (mapped to detection design)

- **MITRE ATT&CK** (`raw/kofi-mitre.md`) — Anomalie Grid's `api/mitre/` route surfaces ATT&CK metadata; Kofi's note is the analyst-side primer.
- **Cyber Kill Chain** / **Unified Kill Chain** (`raw/kofi-cyber-kill-chain.md`, `raw/kofi-unified-kill-chain.md`) — phase model for actor-centric investigation. Direct fit for [[Actor Profiling]].
- **Diamond Model** (`raw/kofi-diamond-model.md`) — adversary / capability / infrastructure / victim. Maps to actor → capability → infra graph in the dashboard.
- **Pyramid of Pain** (`raw/kofi-pyramid-of-pain.md`) — IOC value hierarchy. Argues why passive fingerprinting (TLS/JA3) is high-value detection: TTPs at the tip > hashes at the base.

## SOC operations (analyst workflow)

- `raw/kofi-soc-fundamentals.md`, `raw/kofi-intro-to-siem.md`, `raw/kofi-intro-to-edr.md` — describe the L1 analyst loop. Anomalie Grid's mission-control + alert workflow should read like an EDR/SIEM hybrid to this audience.

## Detection content sources

- `raw/kofi-yara.md`, `raw/kofi-sysmon.md` — pattern matching + Windows host telemetry. Detection-engineering inputs.
- `raw/kofi-threat-intel-tools.md`, `raw/kofi-intro-to-cti.md` — CTI pivot tooling, feeds Anomalie Grid's intel route.

## What to do next with this material

- If Anomalie Grid messaging needs analyst-buyer language, lift phrasing directly from kofi-soc-fundamentals and kofi-intro-to-siem (these are pre-written in TryHackMe's clean instructional voice).
- If wiki/[[Actor Profiling]] needs a Diamond/Kill Chain framing, pull from kofi-diamond-model + kofi-cyber-kill-chain.
- If a "Red Pill onboarding" node is added, anchor it to kofi-anomaly-grid-architecture (Kofi already named it).

## Related

- [[Anomalie Grid]] · [[The Oracle]] · [[The Architect]] · [[Nebuchadnezzar]] · [[Zion]] · [[Sentinel Swarm]] · [[The Construct]] · [[Actor Profiling]]
