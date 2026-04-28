---
type: connector
tags:
  - connector
  - publishing
  - video
  - application
entity: OpenClaw
---
# YouTube

Video publishing connector linked from [[OpenClaw]].

## Description

This note represents YouTube as a publishing/distribution surface connected to [[OpenClaw]].
It is the channel for posting demo recordings, architecture walkthroughs, founder content, and any long-form video output produced by Intellusia.

## Why it matters

Video is one of the highest-leverage distribution surfaces for technical credibility (see [[SAAS_TRENDS]] — distribution via developer/operator audiences). Keeping YouTube as a distinct connector node makes it visible in the operations graph and easier to automate via [[OpenClaw]].

## Typical workflows

- Publish [[Playbooks/Demo Playbook]] recordings (5-min cold demos, 30-min scoped demos).
- Publish architecture walkthroughs aligned with [[VOICE_AND_STYLE]].
- Publish founder content tied to [[WORLD_VIEW]] trend captures.
- Cross-post or excerpt clips to other [[OpenClaw]] surfaces (Discord, social).

## Connection notes

- Auth: YouTube Data API v3 OAuth credentials, stored outside the vault.
- Automation surface: upload, schedule, metadata (title, description, tags, thumbnail).
- Keep credentials in the secret store referenced by [[OpenClaw]], never in this vault.
