---
title: Demo Playbook
type: playbook
tags:
  - playbook
  - demo
  - sales
entity: Intellusia Studios
updated: 2026-04-27
---

# Demo Playbook

How [[Anomalie Grid]] gets demoed. Every demo is staged for a specific persona at a specific stage in [[Client Journey]].

See also: [[Buyer Personas]], [[VOICE_AND_STYLE]], [[Connection Surfaces]]

## Demo formats

### 5-minute demo (cold call follow-up, conference, hallway)

Goal: earn the 30-minute demo.

Show:
1. [[Zion]] homepage with a single high-confidence finding.
2. One click into the finding to expose [[The Oracle]]'s reasoning chain.
3. The honeynet ([[The Construct]]) badge on the finding showing it was attacker-corroborated.

Say: "This is what your SOC sees. Behind it: [[Sentinel Swarm]] collectors, [[Nebuchadnezzar]] on Morpheus inference, [[The Oracle]] doing the prioritization. Want 30 minutes to see how it deploys?"

End: calendar link.

### 30-minute demo (scoped first call)

Goal: earn the pilot conversation.

Structure:
- 3 min — the prospect describes their environment (listen first).
- 5 min — architecture overview using [[Samples/Architecture One Pager]].
- 12 min — live walkthrough of [[Zion]] with 3 real finding types: lateral movement, identity anomaly, deception trip.
- 5 min — [[Tenant Model]] and [[The Architect]] walkthrough for credibility.
- 5 min — pilot scoping conversation.

Anti-patterns:
- Slides before product.
- Demo without listening to their environment first.
- Walking through every feature.

### 60-minute deep dive (post-pilot interest)

Goal: earn the SOW.

Structure:
- 5 min — recap from prior call.
- 10 min — [[ADRs/ADR-001 Multi-tenant cells]] walkthrough.
- 15 min — [[Operations/Eval Framework]] and how we measure quality.
- 15 min — full [[Connection Surfaces]] tour including APIs and integrations.
- 10 min — pilot SOW outline using [[Samples/Pilot SOW]].
- 5 min — close: signed SOW or scheduled follow-up.

## Per-persona demo emphasis

| Persona | Lead with | Spend most time on | Avoid |
| --- | --- | --- | --- |
| CISO | Outcome + posture | [[The Architect]], [[Tenant Model]] | Prompt internals |
| SOC manager | Findings + ATT&CK mapping | [[Zion]], [[The Oracle]] reasoning | Pricing |
| Cloud architect | Topology + isolation | [[Tenant Model]], [[ADRs]] | Marketing language |
| GRC | Audit + residency | [[The Architect]] audit log, region pinning | Anything that smells like beta |
| Fed program lead | Vehicles + compliance roadmap | [[Government Contracting Pipeline]] story | Production claims we can't back |

## Demo environment

- Always demo on a **demo tenant**, not on staging or any client tenant.
- Demo tenant has curated, anonymized findings — never real client data.
- Refresh demo tenant findings monthly so the same prospect doesn't see stale content twice.
- Have a backup recording for every demo type in case of network failure.

## Failure modes

- Demoing without confirming the prospect's environment first → wrong findings shown.
- Demo running long → the close conversation gets skipped, and the deal stalls.
- Showing roadmap features as if they exist → kills trust on the next call.
- Talking through the demo instead of letting findings speak → looks like marketing, not product.

## Post-demo within 24 hours

- Send recap email with three things they cared about.
- Send relevant artifact (architecture one-pager, pilot SOW, briefing template) attached.
- Calendar link for the next step.
- Log notes in [[Operations/Account Research Template]].
