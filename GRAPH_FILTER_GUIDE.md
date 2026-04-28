---
title: Graph Filter Guide
type: guide
tags:
  - guide
  - graph
  - obsidian
  - filtering
entity: Intellusia Studios
updated: 2026-04-27
---

# GRAPH_FILTER_GUIDE

This guide explains how to use the vault's metadata and tags to make the Obsidian graph useful instead of noisy.

Related notes:
- [[INTELLUSIA_GRAPH]]
- [[MEMORY]]

## Why filtering matters

This vault has two layers:

1. **Core nodes**
   - company
   - product
   - components
   - infrastructure
   - capabilities
   - connectors

2. **Relationship nodes**
   - notes beginning with `Rel - ...`
   - used to make the graph denser and more realistic
   - useful for systems mapping
   - optional when you want a cleaner view

The goal is to switch views depending on what you are trying to understand.

## Metadata model

### Main `type` values

- `company`
- `product`
- `component`
- `connector`
- `infrastructure`
- `capability`
- `workflow`
- `operations`
- `graph-hub`
- `master-memory`
- `relationship`
- `guide`

### Important tags

- `company`
- `product`
- `component`
- `connector`
- `infrastructure`
- `capability`
- `workflow`
- `operations`
- `memory`
- `graph-hub`
- `relationship`
- `hideable`
- `guide`

## Relationship color scheme

Each relationship note has a `color` frontmatter field and a semantic tag for use in Obsidian's Graph View **Groups** panel.

### Intellusia → outbound

| Color | Tag | Relationship | Meaning |
|-------|-----|--------------|---------|
| Red | `rel-product` | Intellusia → Anomalie Grid | Flagship product, primary commercial narrative |
| Blue | `rel-infrastructure` | Intellusia → Azure Terraform Work | Infrastructure delivery, Azure-first credibility |
| Green | `rel-market` | Intellusia → Government Contracting Pipeline | Market opportunity, business growth |
| Orange | `rel-operations` | Intellusia → OpenClaw | Operational automation, connector layer |
| Purple | `rel-capability` | Intellusia → Project Babel | AI fluency, knowledge, educational portfolio |
| Yellow | `rel-identity` | Intellusia → Operator Profile | Founder decision model, self-duplication anchor |
| Cyan | `rel-intelligence` | Intellusia → World View | External market radar, trend tracking |

### Anomalie Grid → outbound

| Color | Tag | Relationship | Meaning |
|-------|-----|--------------|---------|
| Pink | `rel-client` | Anomalie Grid → Client Connection | Client-facing SaaS surface, buyer journey |

### OpenClaw → outbound

| Color | Tag | Relationship | Meaning |
|-------|-----|--------------|---------|
| Violet | `rel-ai` | OpenClaw → Claude, OpenRouter | AI reasoning and model routing |
| Indigo | `rel-messaging` | OpenClaw → Discord, Telegram, WhatsApp | Messaging and notification channels |
| Blue | `rel-infrastructure` | OpenClaw → Hostinger VPS | Compute and hosting surface |
| Teal | `rel-tooling` | OpenClaw → Postman MCP | API automation and MCP tooling |
| Blue | `rel-video` | OpenClaw → YouTube | Video publishing and distribution |

To apply colors in Obsidian graph view:
1. Open Graph View → click the settings icon (top right)
2. Go to **Groups**
3. Add a group per tag above (e.g. `tag:rel-product`) and assign the matching color

## Alternative views (besides global graph)

| View | How to open | Best for |
|------|------------|---------|
| **Local graph** | Right-click any note → Open local graph | Single node's immediate connections — much cleaner than global |
| **Backlinks pane** | Right panel → Backlinks icon | See what links INTO the current note |
| **Outlinks pane** | Right panel → Outlinks icon | See what the current note links OUT to |
| **Tags pane** | Left panel → Tags icon | Browse all notes by tag — filter by `rel-product`, `component`, etc. |
| **Search** | Ctrl+Shift+F | Full text + frontmatter search across all notes |
| **Dataview plugin** | If installed: inline queries | Query notes like a database — e.g., all `type: component` in a table |

**Recommended for daily use:** Local graph from INTELLUSIA_GRAPH at depth 2, with `tag:relationship` hidden. Faster and less noisy than the global graph.

## Most useful default filter

If the graph feels too busy, start by hiding relationship notes:

- `tag:relationship`

That removes the connector layer and leaves the cleaner structural map.

## Recommended graph views

## 1. Full system map

Use when:
- you want to understand the whole company map
- you want to see how OpenClaw, Anomalie Grid, and company capabilities connect

Settings:
- keep all notes visible
- do **not** hide relationship notes

Expected result:
- denser graph
- relationship nodes visible
- better systems-style structure

## 2. Clean executive map

Use when:
- you want a fast company overview
- you want to see the main nodes only

Hide:
- `tag:relationship`

Focus on:
- `Intellusia Studios`
- `Anomalie Grid`
- `OpenClaw`
- `Government Contracting Pipeline`
- `Azure Terraform Work`
- `Project Babel`
- `MEMORY`
- `INTELLUSIA_GRAPH`

## 3. Product architecture view

Use when:
- you want to focus on Anomalie Grid only
- you want to inspect the product subgraph

Show or focus on:
- `tag:product`
- `tag:component`
- `tag:workflow`

Useful nodes:
- `Anomalie Grid`
- `Sentinel Swarm`
- `Nebuchadnezzar`
- `The Construct`
- `The Oracle`
- `Zion`
- `The Architect`
- `Red Pill Onboarding`

Optional:
- hide `tag:relationship`

## 4. Operations and connectors view

Use when:
- you want to inspect OpenClaw and connected surfaces
- you want to understand the automation and messaging side

Show or focus on:
- `tag:operations`
- `tag:connector`
- `tag:infrastructure`

Useful nodes:
- `OpenClaw`
- `Discord`
- `Telegram`
- `WhatsApp`
- `Claude`
- `OpenRouter`
- `Postman MCP`
- `Hostinger VPS`

Optional:
- keep `tag:relationship` visible if you want the connector layer
- hide `tag:relationship` if you want only direct app nodes

## 5. Capability map

Use when:
- you want to see what Intellusia can build or sell beyond the flagship

Show or focus on:
- `tag:capability`
- `tag:infrastructure`
- `tag:product`

Useful nodes:
- `Government Contracting Pipeline`
- `Azure Terraform Work`
- `Project Babel`
- `Anomalie Grid`

## Practical filter recipes

### Simplest cleanup

Hide:
- `tag:relationship`

### Only company and offerings

Focus on:
- `tag:company OR tag:product OR tag:capability`

### Only technical architecture

Focus on:
- `tag:product OR tag:component OR tag:infrastructure`

### Only OpenClaw ecosystem

Focus on:
- `tag:operations OR tag:connector`

### Only memory and navigation notes

Focus on:
- `tag:memory OR tag:graph-hub OR tag:guide`

## How to think about relationship notes

Relationship notes are there to improve the graph shape.

Keep them visible when:
- mapping the whole system
- trying to understand indirect structure
- making the graph look more like a network than a starburst

Hide them when:
- you want a cleaner executive overview
- you are navigating quickly
- you care more about entities than relationships

## Suggested workflow

1. Open `[[INTELLUSIA_GRAPH]]`
2. Start with relationship notes hidden
3. Review the main company and product nodes
4. Turn relationship notes back on when you want the fuller systems map
5. Use `[[MEMORY]]` when you need context, not just structure

## Good defaults

If you only want one reliable setup:

- Open local graph from `[[INTELLUSIA_GRAPH]]`
- Set depth to `2` or `3`
- Hide `tag:relationship`

That usually gives the cleanest useful map.
