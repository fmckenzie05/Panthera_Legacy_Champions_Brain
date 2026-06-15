---
type: infrastructure
tags:
  - infrastructure
  - hosting
  - connector
entity: ScriptLabs Studios
updated: 2026-06-04
---
# Hostinger VPS

Infrastructure compute node for **ScriptLabs Studios**.

## Role

Primary runtime for **Hermes** (NousResearch fine-tuned LLM). All AI-driven automation for the ScriptLabs agentic delivery pipeline runs here.

## Why it matters

Self-hosted compute = no per-token API cost at scale. The model is fine-tuned for ScriptLabs dev workflows — not a generic API call. Keeping this node visible in the graph makes infra dependencies explicit.

## Risk

Single node — if VPS goes down, Hermes goes down. [[OpenRouter]] is the pre-configured fallback for model routing.

## Connection notes

- Runs: Hermes LLM, [[ScripLabStudio8]] automation workloads, scheduled jobs
- Deploy script: `scripts/scriptlabs-hostinger.sh`
- Credentials kept outside vault in secret store referenced by [[ScripLabStudio8]]
