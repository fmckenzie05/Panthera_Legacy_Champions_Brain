---
title: Onboarding Path
type: workflow
tags:
  - client
  - saas
  - onboarding
entity: Anomalie Grid
updated: 2026-04-27
---

# Onboarding Path

Implementation detail behind [[Red Pill Onboarding]]. This is what actually happens between contract signature and steady state.

Parent: [[CLIENT_CONNECTION]]
See also: [[Red Pill Onboarding]], [[Tenant Model]], [[Connection Surfaces]]

## Phases

### Phase 0 — kickoff (week 1)

- Confirm scope, tenants, region pinning, integration list.
- Identify client champion, security ops contact, integration engineer.
- Schedule briefings cadence.

### Phase 1 — provisioning (week 1-2)

- [[The Architect]] creates the tenant(s) with region and RBAC.
- SSO/IdP integration validated.
- API keys issued, scoped per tenant.

### Phase 2 — collector deployment (week 2-3)

- [[Sentinel Swarm]] units deployed into client environment.
- mTLS handshake validated; ingestion confirmed end-to-end.
- Identity-source connection wired (when applicable).

### Phase 3 — baseline (week 3-5)

- [[Nebuchadnezzar]] processes incoming telemetry.
- No tenant-facing alerts. Shadow runs only.
- Baseline behavioral profile established per tenant.

### Phase 4 — portal activation (week 5)

- [[Zion]] turns on for tenant users.
- [[The Oracle]] starts producing prioritized recommendations.
- Alerting integrations tested.

### Phase 5 — first briefing (week 5-6)

- Intellusia delivers first formal briefing covering: baseline summary, top findings, recommended next-step actions.
- This is the moment the client sees the product story land.

### Phase 6 — operate (ongoing)

- Quarterly briefings continue.
- Expansion conversations begin at month 4-6 (see [[Renewal And Expansion]]).

## Critical success factors

- Baseline period must be respected — early alerting before baseline kills trust.
- First briefing must surface at least one non-obvious finding.
- Integrations must be functional before phase 5 (alerts to client SIEM/Slack/ITSM).

## Common failure modes

- Skipping baseline because the client is impatient — leads to noisy alerts and lost confidence.
- Under-instrumented [[Sentinel Swarm]] coverage — the platform looks blind.
- No briefing cadence — client forgets the value between events.

## What "good" looks like

- Six-week timeline holds for typical mid-market deployments.
- First briefing produces a finding the client demonstrably could not have surfaced themselves.
- Client champion can articulate the value back to their CISO without Intellusia's help.
