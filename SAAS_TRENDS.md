---
title: SaaS Trends
type: trend
tags:
  - world-view
  - trends
  - saas
entity: Intellusia Studios
updated: 2026-04-27
---

# SAAS_TRENDS

Trends in SaaS architecture, pricing, and GTM that affect how Intellusia ships and sells.

Parent: [[WORLD_VIEW]]
See also: [[CLIENT_CONNECTION]], [[Tenant Model]]

## Trend list

### Usage-based + platform pricing hybrids

- **What:** Pricing combines a platform fee with usage tiers (events ingested, reasoning calls, GPU hours).
- **Why it matters:** [[Anomalie Grid]] has natural usage axes (telemetry volume, Oracle reasoning, retained data). Likely pricing model.
- **Status:** adopting at GTM design time.

### Multi-tenant by design (cell-based architectures)

- **What:** Tenants live in isolated "cells" with shared control planes and isolated data planes.
- **Why it matters:** Aligns with [[The Architect]] and [[Tenant Model]]. This is the right enterprise posture.
- **Status:** core architectural commitment.

### Self-serve gated by white-glove

- **What:** Public docs and trial flow exist, but real onboarding is human until ARR threshold.
- **Why it matters:** [[Red Pill Onboarding]] is intentionally white-glove for the first cohort. Match the trend; do not over-invest in self-serve early.
- **Status:** matches current strategy.

### Embedded / agentic CX

- **What:** AI assistants embedded into the product as the primary interface, not a chat widget bolted on.
- **Why it matters:** [[Zion]] should be designed so [[The Oracle]] is the default investigation surface, not a side panel.
- **Status:** affects [[Zion]] design.

### Distribution via developer/operator audiences

- **What:** Founders building audience through technical writing and demos before sales motion.
- **Why it matters:** Aligns with Intellusia's [[OPERATING_RHYTHM]]. Architecture writing earns enterprise meetings.
- **Status:** core motion.

### Data residency, BYO-cloud, and sovereignty offerings

- **What:** Enterprise buyers requiring deployment in their cloud/region.
- **Why it matters:** Azure-first posture is helpful; need a credible BYO-Azure story for large deals. Connects to [[Azure Terraform Work]].
- **Status:** watching, plan to formalize.

### MCP and tool-marketplace as a SaaS surface

- **What:** SaaS platforms exposing MCP-style tool surfaces to buyers' own AI agents.
- **Why it matters:** [[Anomalie Grid]] could expose its detections/reasoning as tools to buyers' SOC agents. Future surface.
- **Status:** watching.

### Outcome-based contracting

- **What:** Pricing or guarantees tied to measurable outcomes (mean-time-to-detect, alert-to-action time).
- **Why it matters:** [[Anomalie Grid]] could lean into outcome metrics where the architecture supports it. Risky if eval is weak.
- **Status:** watching, gated on eval maturity.

## How to use

When updating [[CLIENT_CONNECTION]] or pricing-related notes, this list is the reference. Tag any trend `adopting` only when it has a corresponding action in a strategy note.
