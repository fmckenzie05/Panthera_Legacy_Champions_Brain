---
title: Intellusia Graph Hub
type: graph-hub
tags:
  - graph-hub
  - map
  - navigation
entity: Intellusia Studios
updated: 2026-04-27
---

# INTELLUSIA_GRAPH

This note exists to make the **Intellusia Studios** system visible in Obsidian's graph.
Obsidian only graphs notes and links that exist inside the vault, so this file acts as the central map for external projects, product nodes, and connected applications without migrating the source material.

Related memory:
- [[HOME]]
- [[MEMORY]]
- [[GRAPH_FILTER_GUIDE]]

## Company core

- [[MEMORY]]
- [[Intellusia Studios]]
- [[Anomalie Grid]]
- [[OpenClaw]]
- [[Government Contracting Pipeline]]
- [[Azure Terraform Work]]
- [[Project Babel]]
- [[OPERATOR_PROFILE]]
- [[WORLD_VIEW]]
- [[CLIENT_CONNECTION]]

## Self-duplication layer

- [[OPERATOR_PROFILE]]
- [[DECISION_PRINCIPLES]]
- [[WORLDVIEW]]
- [[OPERATING_RHYTHM]]
- [[VOICE_AND_STYLE]]

## World view (industry trends)

- [[WORLD_VIEW]]
- [[AI_DESIGN_PATTERNS]]
- [[AI_SECURITY_TRENDS]]
- [[SAAS_TRENDS]]
- [[GOV_TECH_TRENDS]]
- [[TREND_TRACKING_CADENCE]]

## Client to SaaS connection

- [[CLIENT_CONNECTION]]
- [[Buyer Personas]]
- [[Client Journey]]
- [[Tenant Model]]
- [[Connection Surfaces]]
- [[Onboarding Path]]
- [[Renewal And Expansion]]

## Relationship connectors

- [[Rel - Intellusia to Anomalie Grid]]
- [[Rel - Intellusia to Government Contracting Pipeline]]
- [[Rel - Intellusia to Azure Terraform Work]]
- [[Rel - Intellusia to Project Babel]]
- [[Rel - Intellusia to OpenClaw]]
- [[Rel - Intellusia to Operator Profile]]
- [[Rel - Intellusia to World View]]
- [[Rel - Anomalie Grid to Client Connection]]
- [[Rel - OpenClaw to Discord]]
- [[Rel - OpenClaw to Telegram]]
- [[Rel - OpenClaw to WhatsApp]]
- [[Rel - OpenClaw to YouTube]]
- [[Rel - OpenClaw to Claude]]
- [[Rel - OpenClaw to OpenRouter]]
- [[Rel - OpenClaw to Postman MCP]]
- [[Rel - OpenClaw to Hostinger VPS]]

## Anomalie Grid product map

- [[Anomalie Grid]]
  - [[Sentinel Swarm]]
  - [[Nebuchadnezzar]]
  - [[The Construct]]
  - [[The Oracle]]
  - [[Zion]]
  - [[The Architect]]
  - [[Red Pill Onboarding]]

## External project sources

These are the real source locations outside the vault.

- Government Contracting workspace: [Open folder](file:///C:/Users/ferna/OneDrive/Documents/Government_Contracting)
- Anomalie Grid architecture source: [Open folder](file:///C:/Users/ferna/OneDrive/Documents/Government_Contracting/Anomalie_Grid_Project/Anomaly_Grid)
- Anomaly Grid implementation repo: [Open folder](file:///C:/Users/ferna/OneDrive/Documents/Government_Contracting/anomaly-grid)
- ETL pipeline: [Open folder](file:///C:/Users/ferna/OneDrive/Documents/Government_Contracting/ETL_Pipeline/intellusia_etl)
- Terraform/Azure work: [Open folder](file:///C:/Users/ferna/OneDrive/Documents/Government_Contracting/I3_Microsoft_Terraform)
- Project Babel: [Open folder](file:///C:/Users/ferna/OneDrive/Documents/Government_Contracting/claude_pc_coworker/project-babel)

## OpenClaw application connectors

This section maps the applications and surfaces OpenClaw works with at a high level.
Keep credentials out of this vault; only store relationship-level memory here.

- [[OpenClaw]] -> [[Discord]]
- [[OpenClaw]] -> [[Telegram]]
- [[OpenClaw]] -> [[WhatsApp]]
- [[OpenClaw]] -> [[YouTube]]
- [[OpenClaw]] -> [[Claude]]
- [[OpenClaw]] -> [[OpenRouter]]
- [[OpenClaw]] -> [[Postman MCP]]
- [[OpenClaw]] -> [[Hostinger VPS]]

## Why the whole system is not visible by default

Obsidian graph does **not** automatically understand:
- folders outside the vault
- Docker containers
- VPS services
- external apps
- APIs
- integrations

It only sees:
- notes inside the vault
- wikilinks between notes
- markdown links between notes/files/URLs

So if you want the graph to show “Intellusia as a whole,” you need a small layer of vault notes that represent the system.

## Best low-friction setup

Without migrating files, use this pattern:

1. One hub note for the company graph
2. One memory note for stable operating context
3. Small stub notes for each important node
4. External file links back to the real folders

That gives you graph visibility without duplicating the actual source workspace.

## Hiding or showing relationship notes

All relationship notes use:
- `type: relationship`
- `tags: [relationship, connector, hideable]`

So in Obsidian graph view you can hide them by filtering out:
- `tag:relationship`

Or keep them visible when you want the fuller systems map.
