---
title: Wiki Index
type: index
updated: 2026-04-28-repo-ingest
---

# Wiki Index

Master list of every wiki page. Grouped by concept area. One-line description per page.

## Foundations
- [[OPERATOR_PROFILE]] — who Fernando is operating as, role and constraints driving the build
- [[WORLDVIEW]] — internal beliefs about market/AI/security + outward radar of trends (merged from former WORLDVIEW + WORLD_VIEW)
- [[DECISION_PRINCIPLES]] — heuristics that govern build/sell tradeoffs
- [[VOICE_AND_STYLE]] — tone, vocabulary, and brand voice rules
- [[OPERATING_RHYTHM]] — cadence of work, weekly/monthly/quarterly loops
- [[MEMORY]] *(at vault root)* — long-term context for the operator and AI collaborators
- [[Kofi Cyber Synthesis]] — analyst-side cyber/SOC fundamentals (MITRE, Kill Chain, Diamond, Pyramid of Pain) ingested from Kofi; mapped to Anomalie Grid components

## Company / Brand Surface
- [[Intellusia Studios]] — the studio entity itself
- [[Anomalie Grid]] — flagship multi-tenant SaaS product
- [[Anomaly Grid CLI]] — sibling solo-operator Rust CLI product
- [[Project Babel]] — companion initiative
- [[Sentinel Swarm]] — edge collectors (Layer 1 of [[Morpheus Infra Schema]])
- [[Nebuchadnezzar]] — Morpheus + Triton inference engine (Layer 5)
- [[The Architect]] — Matrix-themed component (admin / control plane)
- [[The Construct]] — Matrix-themed component (decoy/honeynet — architectural roadmap, not current beachhead)
- [[The Oracle]] — Matrix-themed component (agentic reasoning over inference outputs)
- [[Zion]] — tenant-facing Next.js portal (Layer 7)
- [[Mission Control]] — operator multi-tenant view (peer of Zion in the same Next.js app)
- [[Red Pill Onboarding]] — branded customer onboarding journey

## Anomalie Grid — capabilities and surfaces
- [[Morpheus Infra Schema]] — the 7-layer architecture document
- [[Telemetry Ingest API]] — `POST /api/telemetry/ingest` contract
- [[Actor Profiling]] — actor-centric event grouping (FR-4)
- [[Passive Fingerprinting]] — device + session fingerprint pipeline
- [[MITRE Coverage]] — TTP mapping surface and `/api/mitre/coverage`
- [[Anomaly Grid Build Status]] — implemented vs. designed delta (snapshot 2026-04-15)
- [[Anomaly Grid PRFAQ]] — press-release positioning + messaging guardrails

## Client & Go-To-Market
- [[CLIENT_CONNECTION]] — overarching model for how clients interface with Intellusia
- [[Client Journey]] — phased path from first contact to renewal
- [[Connection Surfaces]] — the specific touchpoints clients hit
- [[Onboarding Path]] — operational steps for bringing a client on
- [[Red Pill Onboarding]] — the deliberately white-glove first-ten-clients process
- [[Renewal And Expansion]] — what drives keep + grow motions
- [[Buyer Personas]] — who buys, with what budget, against what mandate
- [[Tenant Model]] — multi-tenant architecture posture as a sales asset

## Government Contracting
- [[Government Contracting Pipeline]] — overview of the gov-side pipeline
- [[GOVERNMENT_CONTRACTING_PIPELINE_STRATEGY]] — strategic playbook for the gov pipeline

## Trends Subnotes (feed [[WORLDVIEW]])
- [[AI_DESIGN_PATTERNS]] — agent scaffolding, RAG, MCP, evals, multi-agent, memory
- [[AI_SECURITY_TRENDS]] — what is moving in cyber + AI
- [[SAAS_TRENDS]] — multi-tenant, pricing, GTM, distribution
- [[GOV_TECH_TRENDS]] — federal AI, FedRAMP, procurement signals
- [[TREND_TRACKING_CADENCE]] — sources, review cadence, how to capture

## ScriptLabs Studio Tools
- [[Claude]] — Claude as a connector node
- [[Discord]] — Discord as a connector node
- [[Hostinger VPS]] — hosting connector
- [[OpenRouter]] — model routing connector
- [[Postman MCP]] — MCP / API connector
- [[Telegram]] — Telegram connector
- [[WhatsApp]] — WhatsApp connector
- [[YouTube]] — YouTube connector
- [[Azure Terraform Work]] — Azure infra automation surface

## Relationship Edges (Obsidian graph)
- [[Rel - Intellusia to ScriptLab_I3]] — **gold / rel-brand** — Intellusia I3 (holding) → ScriptLabs Studios (sales face)
- [[Rel - Intellusia to Anomalie Grid]]
- [[Rel - Intellusia to Anomaly Grid CLI]]
- [[Rel - Intellusia to Azure Terraform Work]]
- [[Rel - Intellusia to Government Contracting Pipeline]]
- [[Rel - Intellusia to Operator Profile]]
- [[Rel - Intellusia to Project Babel]]
- [[Rel - Intellusia to World View]] — *(now points to merged WORLDVIEW; consider renaming)*
- [[Rel - Anomalie Grid to Client Connection]]
- [[Rel - Anomalie Grid to Kofi Cyber Synthesis]] — **cyan / rel-intelligence** — analyst SOC/cyber knowledge layer
- [[Rel - Anomalie Grid to Anomaly Grid CLI]]
- [[Rel - Anomalie Grid to Mission Control]]
- [[Rel - Nebuchadnezzar to Morpheus Infra Schema]]
- [[Rel - Sentinel Swarm to Telemetry Ingest API]]

## ScriptLab_I3 — LLM Soul Cluster
- [[ScriptLab_I3/_index]] — Hub for ScriptLab_I3 — soul files, workflow, behavioral contract
- [[ScriptLab_I3/LLM_Soul]] — Core LLM persona, system prompt template, identity anchor, and optimization priorities for Hermes
- [[ScriptLab_I3/Studio_Operating_Context]] — Intellusia Agentic Studio operating model, Web3 ramp phases, delivery stack
- [[ScriptLab_I3/Studio_Workflow]] — Agentic delivery workflow: Hermes, GHL+MCP, Claude Code, OpenRouter, messaging, publishing
- [[ScriptLab_I3/Behavioral_Rules]] — Hard behavioral contract: always/never rules, messaging guardrails, delegation boundaries

## External Companies & Reference Nodes
- [[ScripLabStudio8]] — AI-powered dev studio (web/mobile/Web3); reference node for market positioning and potential partnership research

## Examples & Templates
- [[FIRST_POPULATION_NOTE]] — seed example note
- [[EXAMPLE_IDEA_NOTE]]
- [[EXAMPLE_MEETING_NOTE]]
- [[EXAMPLE_PROJECT_UPDATE]]
- [[TEMPLATE_VERIFICATION_NOTE]]

## Playbooks
- [[Playbooks/Demo Playbook]]
- [[Playbooks/Outbound Playbook]]
