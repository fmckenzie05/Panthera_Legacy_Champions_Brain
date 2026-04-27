---
title: Client Journey
type: journey
tags:
  - client
  - saas
  - journey
entity: Intellusia Studios
updated: 2026-04-27
---

# Client Journey

End-to-end view of a client's lifecycle with [[Anomalie Grid]], from first awareness through expansion.

Parent: [[CLIENT_CONNECTION]]
See also: [[Buyer Personas]], [[Onboarding Path]], [[Renewal And Expansion]]

## Stages

### 1. Awareness

- **How they hear:** founder content, technical writing, demo recordings, conference presence, partner referral, gov-procurement signal.
- **What they see first:** a specific outcome (e.g., "honeynet-derived behavioral detection on Azure") not a generic AI-security pitch.
- **Owned by:** founder voice and [[VOICE_AND_STYLE]].
- **Success metric:** they request a demo or open an outbound reply.

### 2. Discovery

- **What happens:** scoping call, environment review, persona identification per [[Buyer Personas]].
- **Surfaces touched:** none yet — pre-product.
- **Owned by:** founder + (eventually) sales engineer.
- **Success metric:** they agree to a pilot scope.

### 3. Pilot / proof

- **What happens:** scoped tenant on [[Anomalie Grid]], a small slice of [[Sentinel Swarm]] collectors, baseline period, [[The Oracle]] producing prioritized output.
- **Surfaces touched:** [[Zion]] (limited), [[The Architect]] (provisioning), API for ingestion.
- **Owned by:** Intellusia delivery + client champion.
- **Success metric:** at least one finding the client could not have produced with their existing stack.

### 4. Onboarding

- **What happens:** [[Red Pill Onboarding]] — full provisioning, baseline, portal activation, first briefing. See [[Onboarding Path]] for detail.
- **Surfaces touched:** all primary surfaces in [[Connection Surfaces]].
- **Owned by:** Intellusia delivery + client security ops.
- **Success metric:** baseline completed, first formal briefing delivered.

### 5. Production / steady state

- **What happens:** continuous telemetry through [[Sentinel Swarm]], inference through [[Nebuchadnezzar]], reasoning through [[The Oracle]], investigations in [[Zion]].
- **Surfaces touched:** [[Zion]] daily, alerts, API for downstream tooling, [[The Architect]] for admin.
- **Owned by:** client SOC + Intellusia support.
- **Success metric:** measurable reduction in time-to-investigate or detection coverage gain.

### 6. Renewal

- **What happens:** see [[Renewal And Expansion]].
- **Owned by:** Intellusia + client champion.
- **Success metric:** auto-renew or upsize.

### 7. Expansion

- **What happens:** more environments, more tenants, additional connection surfaces, possible referral.
- **Owned by:** Intellusia + client champion.
- **Success metric:** new ARR from same logo.

## Failure modes to watch

- Demo without a scoped pilot path -> client interest goes cold.
- Pilot without a baseline period -> [[The Oracle]] looks noisy unfairly.
- Production without quarterly briefings -> client forgets the value.
- Renewal without expansion conversation -> flat ARR.

## How to use

When evaluating any client conversation, name the stage. Different stages need different artifacts; mismatched-stage outreach is the second most common reason deals stall (after wrong persona).
