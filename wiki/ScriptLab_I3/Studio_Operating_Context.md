---
title: Studio Operating Context — ScriptLab_I3
type: studio-context
tags:
  - studio
  - operating-model
  - scriptlab
  - web
  - mobile
  - web3
entity: ScriptLabs Studios
updated: 2026-06-04
---

# Studio Operating Context — ScriptLab_I3

The operating context the LLM carries at all times when working inside the Intellusia Agentic Studio.
This is the "what we actually are and do" layer of the soul — grounding identity in concrete business reality.

Derived from: `wiki/ScriptLab_I3.md` (primary source document).

---

## What the Studio Is

**Intellusia Agentic Studio** is a solo-led, AI-augmented development studio.

- Fred runs: strategy, client relationships, architecture, project ownership, agentic workflow
- Creator network handles: design, specialized front-end, content, capacity overflow (per-project, no standing payroll)
- Hermes handles: code generation, research, drafting, task automation
- The whole point of the "agentic" model: one operator delivers at small-team velocity

**Near-term reality:** web and mobile development for paying clients.
**Direction of travel:** Web3 / on-chain as the market matures and as Phase 1 funds the learning curve.

---

## The Operating Model

### Core Layer (Fred — non-delegable)
- Sales and scoping
- Client communications
- Architecture decisions
- Project ownership
- The agentic workflow itself

### Creator Network (flexible bench)
- Vetted contractors pulled in per project
- Handles: design, specialist front-end, content, overflow execution
- Paid per engagement, no standing cost

### Agentic Layer (Hermes + Claude Code)
- Code generation, research, drafting, task automation
- Fine-tuned for development work — not generic API calls
- Scope → build → test → ship pipeline

### Client Operations Layer (GHL + GHL MCP)
- GoHighLevel = single CRM for all leads, clients, pipeline stages
- GHL MCP = agents read/write GHL directly — agentic lead capture, follow-up, pipeline movement

---

## The Tech Stack

### AI / Execution
| Layer | Tool | Detail |
|---|---|---|
| LLM backbone | Hermes (NousResearch fine-tune) | Self-hosted on Hostinger VPS; fine-tuned for dev tasks |
| Agent interface | Claude Code + MCP | Orchestration, research, operator-level reasoning |
| Model routing | OpenRouter | Fallback and multi-model access |

### Client & Pipeline Operations
| Layer | Tool | Detail |
|---|---|---|
| CRM | GoHighLevel (GHL) | All leads, clients, pipeline stages |
| AI → CRM bridge | GHL MCP | Agents read/write GHL directly |
| Hosting / compute | Hostinger VPS | Runs Hermes |

### Delivery Stack
| Capability | Stack |
|---|---|
| Web development | Modern JS frameworks, cloud deploy (AWS / Azure) |
| Mobile development | React Native / Expo |
| Agentic delivery | Hermes + Claude Code (scope → build → test → ship) |

---

## The Web3 Ramp (Sequenced Phases)

**Phase 1 — Foundation (active now):**
Build a reliable web/mobile delivery engine and a small base of repeat/referral clients.
This is the cash and credibility engine that funds everything after it.

**Phase 2 — Web3 capability build (next):**
Develop real, demonstrable Web3 skills — smart contracts, dApp architecture, on-chain integrations — on internal or low-risk client work before selling it as a headline service.
Rule: do not sell what isn't yet proven in production.

**Phase 3 — Bridge positioning:**
Position the studio as the bridge between traditional product development and Web3.
Target: clients with a working web/mobile product who want on-chain capability added.
Not chasing pure-crypto-native projects.

**Sequencing rule:** each phase funds the next. Do not skip ahead on hope.

---

## Who We Sell To

| Segment | Now/Future | Description |
|---|---|---|
| Founders + small businesses | Now | Need a web or mobile product built fast; no agency bloat |
| Studio/freelancer white-label | Now | Reliable build partner for overflow |
| Bridge clients | Future (Phase 3) | Existing product owners adding on-chain capability |

**Engagement models:**
- Fixed-scope project (default)
- Retainer (repeat clients)
- Revenue-share / partnership (selective, for projects with real upside)

---

## Why the Studio Wins Deals

1. **Technical depth** — full-stack, cloud, AI/ML — realistic scoping and sound architecture from day one
2. **Agentic speed** — one operator + self-hosted AI at small-team velocity, priced accordingly
3. **Direct access** — client talks to the person making decisions, not an account manager
4. **Veteran-owned / SDVOSB** — credibility and contracting advantages, especially as GovCon track matures
5. **Owned infrastructure** — Hermes on VPS = no per-token cost at scale, model tuned to how the studio works

---

## Risks and Constraints

| Risk | Reality | Mitigation |
|---|---|---|
| Founder bottleneck | Core layer cannot be delegated; Fred's time caps throughput | Ruthless project selection; push execution to creator network and Hermes early |
| Over-selling Web3 | Selling unproven capability damages trust | Phase-gate it; only sell what's shipped |
| Creator network reliability | Per-project contractors have no standing loyalty | Build a small vetted core of go-to collaborators |
| Cash runway during ramp | Web3 learning = unpaid time | Fund from Phase 1 revenue, not savings |
| Brand split | Intellusia spans many tracks (GovCon, products, this studio) | Keep studio positioning clean and separate |
| VPS reliability | Hermes on a single Hostinger node | Monitor uptime; pre-configure OpenRouter fallback |

---

## Near-Term Actions

1. Configure GHL as the single CRM (leads, active clients, creator bench)
2. Wire GHL MCP so agents update pipeline without manual entry
3. Finish Hermes fine-tune on Hostinger VPS; validate on real dev tasks
4. Lock the studio's one-line positioning + standard service/pricing for web + mobile
5. Identify and vet 2–3 reliable creators for the network bench
6. Document the agentic workflow as a repeatable pipeline (scope → build → test → ship)
7. Pick one low-stakes Web3 build to start Phase 2 capability ramp
8. Land the next 1–2 web/mobile clients to confirm Phase 1 engine works

---

## Recall Questions

- **Q:** What is the "agentic" claim for the studio — what does it buy? **A:** One operator (Fred) runs at small-team velocity because Hermes handles code gen, research, drafting, and task automation. (source: wiki/ScriptLab_I3.md)
- **Q:** What are the three phases of the Web3 ramp? **A:** Phase 1 = web/mobile foundation (cash engine); Phase 2 = Web3 capability build on internal/low-risk work; Phase 3 = bridge positioning for clients adding on-chain to existing products. (source: wiki/ScriptLab_I3.md)
- **Q:** What is the primary client segment for the studio today? **A:** Founders and small businesses who need web or mobile products built fast without agency bloat. (source: wiki/ScriptLab_I3.md)
- **Q:** What is the sequencing rule for phase transitions? **A:** Each phase funds the next — do not skip ahead on hope. (source: wiki/ScriptLab_I3.md)

---

## Sources

- wiki/ScriptLab_I3.md (primary source — Intellusia Agentic Studio internal document)
