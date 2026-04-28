---
title: Client to SaaS Connection
type: client-connection-hub
tags:
  - client
  - saas
  - hub
entity: Intellusia Studios
updated: 2026-04-27
---

# CLIENT_CONNECTION

The hub for how clients actually touch [[Anomalie Grid]]. Everything that happens between "a buyer hears about us" and "a tenant is generating value" lives here or links from here.

Related:
- [[Anomalie Grid]]
- [[Red Pill Onboarding]] (the named onboarding workflow)
- [[The Architect]] (admin/control plane)
- [[Zion]] (tenant portal)
- [[OPERATOR_PROFILE]]

## Subnotes

- [[Buyer Personas]] — who buys and what they care about
- [[Client Journey]] — awareness through renewal
- [[Tenant Model]] — how a client maps to platform tenancy
- [[Connection Surfaces]] — concrete touchpoints (portal, API, alerts, support)
- [[Onboarding Path]] — implementation detail behind [[Red Pill Onboarding]]
- [[Renewal And Expansion]] — what good retention looks like

## The connection in one paragraph

A client engages [[Anomalie Grid]] through a guided onboarding ([[Red Pill Onboarding]]) that provisions an isolated tenant via [[The Architect]], deploys [[Sentinel Swarm]] collectors into their environment, establishes a behavioral baseline, and activates [[Zion]] as the tenant-facing portal. From there, [[Nebuchadnezzar]] processes their telemetry, [[The Construct]] adds honeynet-derived intelligence, and [[The Oracle]] turns enriched signals into prioritized, explainable recommendations. The client interacts primarily through [[Zion]], with secondary surfaces via API, alerts, and support channels — all governed by tenant-scoped isolation per [[Tenant Model]].

## Connection invariants

These never bend, regardless of buyer:

- **Tenant isolation is absolute.** No cross-tenant data leakage at any layer.
- **Onboarding is white-glove until ARR threshold.** Self-serve is a future product, not a launch product.
- **Outputs are explainable.** Anything [[The Oracle]] recommends should be traceable back to the signals that produced it.
- **Identity, region, and data residency are enforceable.** [[The Architect]] is the authority.

## How this hub steers product decisions

When designing a feature, ask:

1. Which [[Connection Surfaces]] does it touch?
2. Which [[Buyer Personas]] does it serve?
3. Where does it sit in the [[Client Journey]]?
4. Does it preserve the invariants above?

If those four answers are not crisp, the feature is not ready to build.
