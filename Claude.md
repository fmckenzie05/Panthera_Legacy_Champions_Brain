# CLAUDE.md — LLM Wiki Schema (Karpathy Method)

## Purpose
This vault is a living knowledge base about **[REPLACE THIS LINE WITH YOUR TOPIC]**.
You (the AI) are responsible for reading source documents in `raw/` and maintaining a
structured, interlinked wiki in `wiki/` that grows richer over time.

This vault uses the **Karpathy method**: every concept is reduced to atomic facts, and
every page carries a small deck of recall questions so the wiki doubles as a spaced-review
study system. Knowledge isn't *captured* — it's *retained*.

> Examples of a good Purpose line:
> - "SAM.gov SDVOSB set-aside opportunities and award history for NAICS 541511/541512/493110."
> - "Client [X]'s regulatory environment, key personnel, and prior contract performance."
> - "Zero Trust implementation patterns, Entra ID configuration, and STIG compliance evidence."
> - "CMMC 2.0 Level 2 control families with mapped policy artifacts."
>
> The Purpose line is the only thing you *must* customize. Everything below works as-is.

---

## Folder Structure
- `raw/` — Source documents (PDFs, markdown, articles, transcripts, exports).
  **Read-only.** Never modify, rename, or delete files here.
- `wiki/` — AI-maintained pages. All synthesis, summaries, and cross-references live here.
- `templates/` — Optional manual page templates. Reference only; do not auto-edit.

Three special files inside `wiki/`:
- `wiki/_index.md` — Master list of every wiki page with a one-line description.
- `wiki/_changelog.md` — Append-only log of every ingest run.
- `wiki/_flashcards.md` — Aggregated deck of every page's recall questions, with
  backlinks to the source page. This is the spaced-review surface.

---

## Ingest Workflow
Trigger phrase: *"I added new sources to raw — read them and update the wiki."*

1. **Identify new files.** Compare `raw/` against `wiki/_index.md` and `wiki/_changelog.md`.
   Only process files not already ingested.
2. **Read each new file fully.** PDFs, markdown, text — all fair game.
3. **Extract atomic facts.** Reduce each claim to the smallest verifiable unit — one
   concept, one date, one number, one relationship per fact. No compound claims.
4. **Update existing pages** when a source refines, expands, or contradicts current content.
   Mark contradictions explicitly with `> ⚠️ Conflict:` blocks.
5. **Create new pages** for concepts that don't yet exist. One concept per page.
6. **Link aggressively** using `[[wikilinks]]` to every related concept in the vault.
7. **Generate recall questions.** For every new or updated page, write 3–5 atomic Q&A
   pairs (see Page Formatting Rules). Each question must isolate one fact from the page.
8. **Update `wiki/_flashcards.md`.** Append new Q&A pairs (or replace the page's block if
   the page was updated), each linked back to its source page via `[[wikilink]]`.
9. **Update `wiki/_index.md`** with new pages and one-line descriptions.
10. **Append to `wiki/_changelog.md`**: date, source filename, pages created, pages updated,
    flashcards added, contradictions surfaced.

Before making changes at scale, propose the plan and wait for confirmation.

---

## Page Formatting Rules
Every page in `wiki/` follows this structure:

```markdown
# [Concept Name]

## Summary
2–4 sentences in plain language. Anyone landing here cold should understand the concept.

## Key Points
- Atomic claim one. (source: raw/filename.md)
- Atomic claim two with specific number or date. (source: raw/another-file.pdf, p.4)
- Inferred claim with no direct source. (inferred)

## Recall Questions
- **Q:** Question isolating one fact from Key Points. **A:** Atomic answer. (source: raw/filename.md)
- **Q:** Question on a date or number. **A:** The specific value. (source: raw/another-file.pdf, p.4)
- **Q:** Question on a relationship between concepts. **A:** The relationship. (source: raw/filename.md)

## Related
- [[Adjacent Concept]]
- [[Parent Concept]]

## Sources
- raw/filename.md
- raw/another-file.pdf
```

Hard rules:
- Every claim cites at least one source, or is explicitly marked `(inferred)`.
- Every page links to at least one related page (unless it's a true root concept).
- Every page has 3–5 recall questions. Each question tests exactly one atomic fact and
  is answerable from the page itself. Cite the same source as the underlying claim.
- Filenames in kebab-case: `tokyo-neighborhoods.md`, `cmmc-level-2-controls.md`.
- Never invent a citation. If you don't have a source, don't claim it.

---

## Question-Answering Behavior
When the user asks a question:
1. **Read `wiki/_index.md` first** to see what exists.
2. **Consult wiki pages, not raw files.** Only re-open `raw/` if the wiki is genuinely thin
   on the topic.
3. **Synthesize across pages.** Pull from multiple wiki pages when the question spans them.
4. **Cite specific wiki pages** in the answer (e.g., "per [[Tokyo Neighborhoods]] and
   [[Best Ramen Shops]]…").
5. **Flag uncertainty** when sources disagree, coverage is thin, or claims are inferred.
6. **Suggest the missing source** if the question reveals a gap. Don't guess.

---

## Recall / Review Behavior
Trigger phrase: *"Quiz me"* (optionally: *"Quiz me on [[Page]]"* or *"Quiz me on [topic]"*).

1. Pull questions from `wiki/_flashcards.md` (or filter to the requested page/topic).
2. Ask one question at a time. Wait for the user's answer before revealing the stored answer.
3. After each round, mark the user's recall as hit/miss in your working notes for the session.
4. At the end, summarize: hits, misses, and which pages the misses cluster around — those
   are the pages worth re-reading or expanding.

Do not surface the answer until the user has attempted recall.

---

## Lint Behavior
Trigger phrase: *"Lint the wiki."*

Produce a report covering:
1. **Orphan pages** — no inbound or outbound links.
2. **Broken links** — `[[wikilinks]]` pointing to nonexistent pages.
3. **Concept gaps** — terms referenced across 3+ pages with no dedicated page.
4. **Contradictions** — pages making conflicting claims.
5. **Stale claims** — claims tied only to old sources when newer ones exist.
6. **Uncited claims** — any claim missing a source reference or `(inferred)` tag.
7. **Index drift** — pages that exist but aren't in `_index.md`, or vice versa.
8. **Missing or thin recall decks** — pages with fewer than 3 recall questions, or pages
   whose questions don't appear in `_flashcards.md`.
9. **Compound questions** — recall questions that test more than one fact at once
   (violates atomicity).

For each issue: list the affected files and a recommended fix. Offer to apply fixes
in batch with confirmation.

---

## Session Start Protocol
At the start of every session:
1. Read `wiki/_index.md`.
2. Skim the last 10 entries in `wiki/_changelog.md`.
3. List any files in `raw/` that haven't been ingested yet.
4. Note the size of `wiki/_flashcards.md` and offer a quick recall round if the user wants one.
5. Then wait for instructions.

---

## Constraints
- Never modify, rename, or delete files in `raw/`.
- Never delete a wiki page without explicit user confirmation.
- Prefer updating an existing page over creating a duplicate. Search `wiki/` first.
- Don't fabricate citations or sources.
- Don't fabricate recall answers — every answer must trace to a cited claim on the page.
- Keep recall questions atomic. One fact per question. If a question needs "and," split it.
- When uncertain whether a concept deserves its own page, ask.
