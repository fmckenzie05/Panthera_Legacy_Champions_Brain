---
title: AI Design Patterns
type: trend
tags:
  - world-view
  - trends
  - ai
  - design-patterns
entity: Intellusia Studios
updated: 2026-04-27
---

# AI_DESIGN_PATTERNS

Live list of AI architecture and design patterns that should inform how Intellusia builds.

Parent: [[WORLD_VIEW]]
See also: [[WORLDVIEW]], [[The Oracle]], [[Nebuchadnezzar]]

## Pattern list

### Tool-using LLMs (the real "agents")

- **What:** LLMs that call tools/functions in a loop with structured outputs and observation/action turns.
- **Why it matters:** [[The Oracle]] is exactly this — reasoning over [[Nebuchadnezzar]] outputs and calling tools (lookup, enrich, escalate) to produce next-step recommendations.
- **Status:** adopting.

### Model Context Protocol (MCP)

- **What:** Open protocol for exposing tools, resources, and prompts to LLM hosts.
- **Why it matters:** Already a vault node ([[Postman MCP]]). Likely how [[OpenClaw]] standardizes connector surfaces over time. May become a procurement requirement for enterprise AI.
- **Status:** adopting via [[OpenClaw]].

### Retrieval-augmented generation (RAG)

- **What:** Grounding model output in retrieved documents/embeddings.
- **Why it matters:** Useful for [[Zion]] explanations and customer-facing investigation summaries grounded in tenant-specific telemetry. Not the differentiator, but table stakes.
- **Status:** adopting where it grounds tenant-specific reasoning.

### Agentic workflows / multi-agent

- **What:** Multiple specialized agents coordinated by a planner or shared scratchpad.
- **Why it matters:** [[The Oracle]] could grow into a small specialist set (triager, enricher, communicator). Avoid premature multi-agent design — single capable agent first.
- **Status:** watching, defer until single-agent eval is solid.

### Evaluation harnesses

- **What:** Structured eval suites (golden sets, regression, LLM-as-judge, online metrics).
- **Why it matters:** Without this, [[The Oracle]] cannot ship to a paying client with confidence. Evals are the difference between a demo and a product.
- **Status:** required before [[The Oracle]] hits any tenant.

### Long-context vs. retrieval

- **What:** Million-token context windows reduce some RAG complexity but increase cost/latency.
- **Why it matters:** For [[Zion]] investigations, long-context summaries of an incident timeline may beat chunked RAG. Watch cost-per-investigation.
- **Status:** watching.

### Streaming inference + GPU pipelines

- **What:** GPU-accelerated streaming inference (Morpheus, Triton, batched kernels).
- **Why it matters:** [[Nebuchadnezzar]] is built on this. The trend toward GPU-native data planes in security is moving in our favor.
- **Status:** core to flagship.

### On-device / edge inference

- **What:** Smaller models running close to the data source.
- **Why it matters:** [[Sentinel Swarm]] could host lightweight pre-filters at the edge to reduce backhaul and improve latency.
- **Status:** watching.

### Structured output and constrained generation

- **What:** JSON schema, grammar-constrained decoding, function-call schemas.
- **Why it matters:** Required for any reliable agent calling [[The Architect]] APIs. Default for everything we build.
- **Status:** adopting as a default.

### Memory systems for agents

- **What:** Persistent memory (episodic, semantic, working) for long-running agents.
- **Why it matters:** [[The Oracle]] needs tenant-scoped memory of past investigations. Avoid generic memory libraries — keep it tenant-isolated by design.
- **Status:** designing.

### Eval-driven prompt + scaffolding iteration

- **What:** Treat prompts and scaffolds as code, version them, gate on eval scores.
- **Why it matters:** Aligns with [[DECISION_PRINCIPLES]]: ship sharp, not perfect, but with measurable quality.
- **Status:** required for shipped agent code.

## How to add to this list

Each new pattern entry should follow the same shape: What, Why it matters for Intellusia (link to a node), Status. If a pattern stops being relevant, mark it `discarded` rather than deleting — the history is useful.
