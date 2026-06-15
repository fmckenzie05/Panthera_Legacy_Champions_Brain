---
type: connector
tags:
  - connector
  - provider
  - ai
entity: ScriptLabs Studios
updated: 2026-06-04
---
# OpenRouter

AI model routing connector for **ScriptLabs Studios**.

## Role

Multi-model access layer and fallback when [[Hostinger VPS]] / Hermes is unavailable.
Lets [[ScripLabStudio8]] workflows call different LLMs via a single API endpoint.

## Why it matters

- Cost optimization across tasks (route cheap tasks to cheaper models)
- Hermes fallback so studio delivery never fully stops on VPS downtime
- Access to frontier models for high-reasoning tasks where Hermes isn't sufficient

## Connection notes

- Commercial model: API-based, per-token
- Used by: Claude Code orchestration layer, ScriptLabs studio automation
- Credentials kept outside vault in secret store
