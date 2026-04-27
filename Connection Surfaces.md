---
title: Connection Surfaces
type: surfaces
tags:
  - client
  - saas
  - surfaces
entity: Anomalie Grid
updated: 2026-04-27
---

# Connection Surfaces

The concrete touchpoints between a client and [[Anomalie Grid]]. Every interaction the client has runs through one of these.

Parent: [[CLIENT_CONNECTION]]
See also: [[Tenant Model]], [[Zion]], [[The Architect]]

## Primary surfaces

### Tenant portal — [[Zion]]

- **Purpose:** dashboards, investigations, alerts, briefings, [[The Oracle]] recommendations.
- **Users:** SOC analysts, SOC manager, CISO (read-mostly).
- **Auth:** SSO via tenant IdP, MFA enforced.
- **Why it matters:** this is where the product earns its renewal.

### Admin / control plane — [[The Architect]]

- **Purpose:** tenant admin, RBAC, configuration, audit, health.
- **Users:** tenant admins, Intellusia delivery, support.
- **Auth:** SSO + elevated MFA + RBAC scoping.
- **Why it matters:** this is the procurement-credibility surface.

### Telemetry ingestion — [[Sentinel Swarm]]

- **Purpose:** receive flows, endpoint signals, identity events from client environment.
- **Users:** automated; client platform engineers configure once.
- **Auth:** mTLS, tenant-scoped credentials, rotation policy.
- **Why it matters:** without this, nothing else works.

## Secondary surfaces

### Outbound API

- **Purpose:** push enriched signals, alerts, and reasoning outputs to client SIEM/SOAR/ITSM.
- **Users:** client integration engineers.
- **Auth:** scoped API keys per tenant, rate-limited.
- **Why it matters:** integration friction is a top reason deals stall — make this easy.

### Inbound API / webhook

- **Purpose:** allow client tools (case management, identity providers) to enrich [[The Oracle]] context.
- **Users:** client integration engineers.
- **Auth:** scoped tokens.
- **Why it matters:** unlocks higher-value reasoning.

### Alerts and notifications

- **Purpose:** push prioritized findings via email, Slack, Teams, PagerDuty, ITSM.
- **Users:** SOC.
- **Auth:** tenant-managed integrations.
- **Why it matters:** this is the product's heartbeat to the client.

### Support channel

- **Purpose:** human escalation and briefings.
- **Users:** all client roles.
- **Auth:** ticket portal + scheduled briefings.
- **Why it matters:** during the white-glove phase ([[Red Pill Onboarding]]), this is part of the product.

## Future surfaces (watching)

### MCP / agent-tool surface

- **Purpose:** expose [[Anomalie Grid]] detections and reasoning as tools to the client's own AI agents.
- **Status:** see [[SAAS_TRENDS]] and [[AI_DESIGN_PATTERNS]] — watching, not yet adopting.

### BYO-cloud deployment

- **Purpose:** deploy [[Anomalie Grid]] inside the client's Azure subscription for sovereignty.
- **Status:** see [[SAAS_TRENDS]] — watching, capacity-gated.

## Surface ownership

| Surface | Product owner | Linked node |
| --- | --- | --- |
| Portal | UI/UX | [[Zion]] |
| Admin | Platform | [[The Architect]] |
| Telemetry | Sensors | [[Sentinel Swarm]] |
| APIs | Platform | [[The Architect]] |
| Alerts | Reasoning | [[The Oracle]] |
| Support | Delivery | [[Red Pill Onboarding]] |
