---
title: Outbound Playbook
type: playbook
tags:
  - playbook
  - outbound
  - sales
entity: Intellusia Studios
updated: 2026-04-27
---

# Outbound Playbook

How Intellusia runs outbound for [[Anomalie Grid]]. The point is not volume — it's the smallest, sharpest message that earns a meeting from the right buyer.

Parent: [[CLIENT_CONNECTION]]
See also: [[Buyer Personas]], [[VOICE_AND_STYLE]], [[Client Journey]]

## Operating principles

- **Specificity over volume.** 30 hand-built sequences > 3000 generic sends.
- **Architecture as the hook.** Lead with a named component or a named technique, not "AI security".
- **Earn the meeting in 60 seconds of read time.** No long pitches in cold copy.
- **Land on a calendar invite, not a discovery call.** Reduce friction.

## Target list construction

### Inputs

- ICP signals: enterprise with mature SOC, Azure-heavy stack, regulated industry, recent breach disclosure or AI-strategy hire.
- Source feeds: LinkedIn fit lists, breach disclosures, federal AI use-case inventories (see [[GOV_TECH_TRENDS]]), Azure case studies, conference attendee lists.
- Personas: see [[Buyer Personas]] — primary CISO/SOC manager/cloud architect, secondary GRC and federal program lead.

### Disqualifiers

- No internal SOC.
- Single-vendor maximalist (locked into Microsoft Defender / CrowdStrike top-to-bottom with no integration appetite).
- Sub-$50M revenue (cannot afford the pilot).
- Recently acquired (frozen during integration).

## Sequence shapes

### Sequence A — CISO, mid-market enterprise (5 touches over 3 weeks)

1. **Day 1 — email.** One-paragraph specific observation about their stack + one named [[Anomalie Grid]] component. CTA: "15 minutes to show what we do that your XDR doesn't."
2. **Day 4 — LinkedIn connect.** Reference the email; add one piece of public content (a post, an architecture diagram).
3. **Day 8 — email.** Reframe with an outcome: "If detecting [specific lateral-movement pattern] in your environment is worth 15 minutes, here's the calendar link."
4. **Day 14 — email.** Send a 90-second Loom of [[Zion]] showing one finding type. CTA: "If this resonates, calendar link."
5. **Day 21 — break-up email.** "Closing the loop. If this is interesting later, here's the architecture brief."

### Sequence B — SOC manager, enterprise (6 touches over 4 weeks)

Heavier on technical proof. Replace the architecture brief with [[Samples/Architecture One Pager]] and the Loom with an evals-result snippet.

### Sequence C — Cloud architect, Azure-native shop (4 touches over 2 weeks)

Lead with [[Tenant Model]] and BYO-Azure posture. Architects hate marketing language; lead with diagrams.

### Sequence D — Federal program lead (slower, 8 touches over 8 weeks)

Lead with [[Government Contracting Pipeline]] credibility and a relevant federal AI inventory entry. Expect 90+ day cycles.

## Message frame

Every outbound message:

1. **Hook** — one-sentence observation specific to their environment or industry.
2. **Bridge** — one sentence tying the observation to a named [[Anomalie Grid]] component.
3. **Proof** — one short artifact (Loom, diagram, post, briefing PDF).
4. **Ask** — one calendar link.

If a message has more than 4 sentences, it's wrong.

## Anti-patterns

- "Just checking in" follow-ups (banned).
- Generic AI-security language stripped of [[Nebuchadnezzar]]/[[The Construct]]/[[The Oracle]] specifics.
- "Intro call" CTA — replace with "15 minutes to see X".
- Sending a deck before the first conversation.

## Tracking

Per prospect, log in [[Operations/Decision Log]] (or future CRM):

- Stage in [[Client Journey]].
- Persona match.
- Last touch date and channel.
- Reason for go / no-go.

## What "good" looks like

- 10-15% reply rate on Sequence A.
- 30%+ of replies convert to a 15-minute call.
- 40%+ of those calls advance to a scoped pilot conversation.
- Zero generic copy. Every sequence references something specific to the prospect's environment.
