---
title: Buyer Personas
type: persona
tags:
  - client
  - saas
  - personas
entity: Intellusia Studios
updated: 2026-04-27
---

# Buyer Personas

Who buys [[Anomalie Grid]] and what each persona cares about. Use this when writing copy, designing demos, or sequencing features.

Parent: [[CLIENT_CONNECTION]]
See also: [[VOICE_AND_STYLE]], [[MEMORY]]

## Primary personas

### CISO / Director of Security

- **What they buy on:** risk reduction, board-defensible posture, audit readiness, vendor consolidation rationale.
- **Pain:** alert fatigue, analyst burnout, inability to prove what is being detected vs. missed.
- **Hooks for [[Anomalie Grid]]:** [[The Oracle]] reduces Tier-1 noise; [[The Construct]] adds proactive intelligence; multi-tenant architecture proves operational maturity.
- **Watch out for:** they will ask about FedRAMP/SOC2/ISO posture early. Do not overpromise.

### SOC Manager / Lead Detection Engineer

- **What they buy on:** does it actually catch what their stack misses, fit with existing pipelines, ATT&CK alignment, eval transparency.
- **Pain:** detection coverage gaps, slow time-to-investigate, integration churn.
- **Hooks for [[Anomalie Grid]]:** [[Nebuchadnezzar]] on Morpheus is a credible detection story; [[The Oracle]] outputs map to ATT&CK; honeynet data from [[The Construct]] is something they cannot get elsewhere.
- **Watch out for:** they want to see the eval methodology. Do not show them adjective-heavy decks.

### Cloud / Platform Architect

- **What they buy on:** clean integration, tenant isolation, Azure-native deployment, BYO-cloud feasibility.
- **Pain:** vendor sprawl in cloud security, fragile integrations, data residency compliance.
- **Hooks for [[Anomalie Grid]]:** Azure-first posture, [[The Architect]] as a real control plane, [[Tenant Model]] designed cell-based.
- **Watch out for:** they will probe for hand-waving on multi-tenant. Be precise.

### Compliance / GRC lead (secondary, gating)

- **What they buy on:** audit trails, data residency, contractual posture, certifications.
- **Pain:** evidence collection, vendor risk reviews, regional data law compliance.
- **Hooks:** [[The Architect]] audit surface, tenant-scoped data, regional deployment via [[Azure Terraform Work]].
- **Watch out for:** they kill deals quietly. Pre-empt their checklist.

## Secondary personas (gov-track)

### Federal / agency program lead

- **What they buy on:** vehicle availability, prime/sub posture, compliance roadmap (FedRAMP, CMMC), pilot funding.
- **Pain:** procurement friction, compliance burden, tying AI to mission outcomes.
- **Hooks:** [[Government Contracting Pipeline]], [[GOVERNMENT_CONTRACTING_PIPELINE_STRATEGY]], pilot-friendly architecture.
- **Watch out for:** long cycles; only pursue if capacity allows per [[GOV_TECH_TRENDS]].

## Anti-personas (do not chase)

- **Tire-kicker MSSPs** looking for a free white-label.
- **Single-analyst teams** with no budget authority.
- **AI-curious enterprises** with no security team — they cannot deploy us.

## How to use

When writing any client-facing artifact, name the persona it targets at the top of the draft. Mismatched persona is the most common reason copy fails.
