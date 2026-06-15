---
title: Studio Workflow — ScriptLab_I3
type: workflow
tags:
  - workflow
  - agentic
  - hermes
  - ghl
  - studio
entity: ScriptLabs Studios
updated: 2026-06-04
---

# Studio Workflow — ScriptLab_I3

The complete agentic delivery workflow and tool stack for **ScriptLabs Studios**.
This defines how the studio actually runs — every tool the LLM (Hermes) and operator (Fernando) touch to move client work from inquiry to delivery.

---

## Workflow Stack

```
ScriptLabs Studios
├── AI Layer
│   ├── Hermes (primary LLM — Hostinger VPS)
│   ├── Claude Code + MCP (orchestration / operator reasoning)
│   └── OpenRouter (model fallback + multi-model access)
├── CRM / Pipeline Layer
│   ├── GoHighLevel (GHL) — all leads, clients, pipeline stages
│   └── GHL MCP — agentic read/write into GHL
├── Messaging / Distribution Layer
│   ├── Discord
│   ├── Telegram
│   └── WhatsApp
├── Publishing Layer
│   └── YouTube
├── Infrastructure
│   └── Hostinger VPS (Hermes runtime + persistent compute)
└── API / Dev Tools
    └── Postman MCP (API testing + integration)
```

---

## Tool Details

### Hermes (Primary LLM)

| Field | Value |
|---|---|
| Base model | NousResearch fine-tune |
| Deployment | Self-hosted, [[Hostinger VPS]] |
| Specialization | Development tasks — code gen, research, drafting, task automation |
| Cost profile | No per-token API cost at scale |
| Fine-tune target | Dev-workflow aligned; not a generic assistant |
| Risk | Single-node — VPS down = model down; [[OpenRouter]] is the fallback |

### Claude Code + MCP

| Field | Value |
|---|---|
| Role | Orchestration, operator-level reasoning, vault management |
| Access | MCP protocol — connects to GHL, Postman, and other MCP servers |
| Relationship to Hermes | Hermes handles execution volume; Claude Code handles high-reasoning orchestration |

### OpenRouter

| Field | Value |
|---|---|
| Role | Fallback and multi-model routing |
| Use case | When Hermes is unavailable or a task needs a different model |
| Commercial model | API-based, per-token |

### GoHighLevel (GHL)

| Field | Value |
|---|---|
| Role | Single CRM for all leads, active clients, and creator network bench |
| Pipeline stages | Leads → Qualified → Scoping → Active → Delivered → Renewal |
| Integration | GHL MCP community server — agents read/write without manual entry |
| Strategic value | Agentic lead capture, follow-up, and pipeline movement with no manual handoffs |

### GHL MCP

| Field | Value |
|---|---|
| Role | Bridge between agentic layer and GHL CRM |
| Capability | Read contacts, write notes, update pipeline stages, trigger automations |
| Status | Near-term action item — wire before client volume scales |

### Messaging: Discord / Telegram / WhatsApp

| Field | Value |
|---|---|
| Role | Operator and client communication surfaces |
| Telegram | Founder-level alerts and real-time status pings |
| WhatsApp | Client and prospect outreach; follow-up workflows |
| Discord | Team / creator network coordination; community engagement |

### Hostinger VPS

| Field | Value |
|---|---|
| Role | Primary compute node for Hermes runtime and automation workloads |
| Status | Existing operational infrastructure |
| Risk | Single point of failure — [[OpenRouter]] fallback must be pre-configured |
| Action | Set up uptime monitoring |

### Postman MCP

| Field | Value |
|---|---|
| Role | API contract validation, connector integration testing |
| Use case | Test integrations (GHL API, YouTube API, etc.) before production |

---

## How the Workflow Flows (Agentic Pipeline)

```
Inbound trigger (client inquiry / task / message)
    ↓
GHL MCP — capture lead, route to pipeline stage
    ↓
Hermes — primary reasoning and execution
    ↓ (complex orchestration / vault work)
Claude Code + MCP
    ↓
Output: code · draft · research · CRM update · message
    ↓
GHL MCP — update pipeline stage, log activity
```

**Fallback path:**
```
Hermes unavailable → OpenRouter → alternate model → continue
```

---

## Near-Term Configuration Actions

1. Configure GHL pipeline stages (Leads → Qualified → Scoping → Active → Delivered → Renewal)
2. Wire GHL MCP so agents update pipeline without manual entry
3. Validate Hermes fine-tune on Hostinger VPS with 3 real dev tasks before client work
4. Pre-configure OpenRouter fallback route
5. Set up Hostinger VPS uptime monitoring
6. Configure Postman MCP for GHL API and YouTube API test coverage

---

## Recall Questions

- **Q:** What is GHL's role in the ScriptLabs workflow? **A:** Single CRM for all leads, clients, and pipeline — GHL MCP lets agents read/write it directly without manual entry. (source: wiki/ScriptLab_I3/Studio_Workflow.md)
- **Q:** What is the fallback when Hermes is unavailable? **A:** OpenRouter for multi-model access. (source: wiki/ScriptLab_I3/Studio_Workflow.md)
- **Q:** Why is Hermes self-hosted? **A:** No per-token cost at scale; fine-tuned specifically for the studio's dev workflow. (source: wiki/ScriptLab_I3/Studio_Workflow.md)
- **Q:** What is the end-to-end agentic pipeline flow? **A:** Inbound trigger → GHL MCP (capture) → Hermes (execution) → Claude Code (if complex) → Output → GHL MCP (update pipeline). (source: wiki/ScriptLab_I3/Studio_Workflow.md)

---

## Sources

- wiki/ScriptLab_I3.md (studio operating document)
- wiki/ScriptLab_I3/LLM_Soul.md
