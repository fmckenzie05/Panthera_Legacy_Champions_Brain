---
title: Trend Tracking Cadence
type: process
tags:
  - world-view
  - cadence
  - process
entity: Intellusia Studios
updated: 2026-04-27
---

# TREND_TRACKING_CADENCE

How [[WORLD_VIEW]] stays current. The point is not to consume the most signal — it is to update the build and the pitch when something real changes.

Parent: [[WORLD_VIEW]]
See also: [[OPERATING_RHYTHM]]

## Sources to scan

### High-signal (weekly)

- Anthropic, OpenAI, NVIDIA, Microsoft AI engineering blogs.
- NVIDIA Morpheus releases and AI security blog.
- CISA advisories and zero-trust guidance.
- Federal AI use-case inventories.
- Selected security vendor research (CrowdStrike, Wiz, Palo Alto Unit 42).

### Medium-signal (monthly)

- MITRE ATT&CK updates.
- Major AI conference proceedings (NeurIPS, ICML, RSA, Black Hat).
- FedRAMP and CMMC policy updates.
- SaaS pricing and GTM writing from operator-led publications.

### Low-signal (ambient)

- AI/security newsletters.
- Operator-leaning podcasts.
- Twitter/X for raw rumor and pattern-spotting.

Treat low-signal sources as inspiration only. Nothing should change [[Anomalie Grid]] based on a tweet.

## Capture protocol

When something matters:

1. Open the relevant subnote ([[AI_DESIGN_PATTERNS]], [[AI_SECURITY_TRENDS]], [[SAAS_TRENDS]], [[GOV_TECH_TRENDS]]).
2. Add a new entry using the standard shape: What, Why it matters, Source (with date), Status.
3. If the trend should change a build or pitch decision, also update the relevant strategy or component note.
4. If the trend is noise, do not add it. Discipline the list.

## Review cadence

- **Weekly:** scan high-signal sources, capture nothing or capture briefly.
- **Monthly:** review every `watching` entry. Promote to `adopting`, demote to `discarded`, or leave with a refreshed date.
- **Quarterly:** re-read [[WORLDVIEW]] and update beliefs if the trend evidence demands it.

## What "good" looks like

- Every entry in the trend subnotes has a source and a date.
- No entry has been `watching` for more than two quarters without a decision.
- Every `adopting` entry has a corresponding action visible in a strategy or component note.

If those three things are true, the world-view layer is working.
