---
title: Tenant Model
type: architecture
tags:
  - client
  - saas
  - tenancy
  - architecture
entity: Anomalie Grid
updated: 2026-04-27
---

# Tenant Model

How a client maps to platform tenancy in [[Anomalie Grid]]. This is an invariant of the product — see [[CLIENT_CONNECTION]].

Parent: [[CLIENT_CONNECTION]]
See also: [[The Architect]], [[Zion]], [[Sentinel Swarm]]

## Tenant definition

A **tenant** is the unit of isolation. One client maps to one or more tenants depending on legal entity, region, or environment separation needs.

A tenant has:

- A unique tenant ID and namespace across all [[Anomalie Grid]] components.
- Region pinning (data residency).
- An isolated data plane (telemetry storage, inference state, Oracle memory).
- A shared control plane via [[The Architect]] with strict RBAC.
- Its own [[Zion]] portal scope.

## Isolation guarantees

- **Data plane:** no cross-tenant queries, ever. Storage is tenant-keyed at rest and in transit.
- **Inference:** [[Nebuchadnezzar]] processes tenant data in tenant-scoped pipelines. Models are shared; data is not.
- **Reasoning memory:** [[The Oracle]]'s memory is tenant-scoped. No tenant-A signals leak into tenant-B reasoning.
- **Honeynet:** [[The Construct]] feeds learnings back into shared model improvements only via fully sanitized, anonymized derivative signals. Raw attacker data per honeynet stays scoped.
- **Admin:** [[The Architect]] enforces RBAC, audit, and lifecycle. Tenant admins cannot see other tenants.

## Tenant lifecycle

1. **Provision** — [[The Architect]] creates tenant, region pin, RBAC roles, and portal access.
2. **Deploy collectors** — [[Sentinel Swarm]] units pushed into client environment.
3. **Baseline** — telemetry collected, behavioral baseline established, no alerts surfaced.
4. **Activate** — [[Zion]] alerts and [[The Oracle]] recommendations turn on.
5. **Operate** — continuous; periodic briefings, configuration changes, additional collectors.
6. **Suspend / wind down** — data export, scheduled deletion, audit log archive.

## Multi-environment clients

A single client can have multiple tenants for:

- Production vs. staging segregation.
- Geographic data residency (EU, US-Federal, etc.).
- Subsidiary or business-unit isolation.

[[The Architect]] supports a parent-account abstraction so billing, ownership, and reporting can roll up across tenants while data isolation stays absolute.

## Why this matters

This model is the foundation for every enterprise sale. A weak tenant story kills deals during procurement review (see Compliance/GRC persona in [[Buyer Personas]]). The model also dictates engineering: cell-based deployment, tenant-keyed storage, and tenant-scoped inference are non-negotiable.
