# CLAUDE.md — Schema for the Computational & Systems Biology Wiki

This repository is an **LLM-maintained wiki**. You (the LLM) own the `wiki/` directory
entirely: you create, update, cross-link and lint its pages. The human owns `raw/`
(sourcing) and asks the questions.

---

## 1. Purpose and scope

A personal knowledge base covering the **two Computational & Systems Biology modules at
Universität Hamburg (UHH)**, reconstructed from the user's **handwritten lecture and
exercise summaries**.

Goals:

- One coherent, interlinked English reference for both modules.
- Every algorithm expressed as **pseudocode**.
- Every process, pipeline, network or structure expressed as a **Mermaid diagram**.
- Exam-ready: definitions, worked examples, complexity, pitfalls.

### Language
**All wiki content is written in English**, even though sources may be German or mixed.
Keep the original German term in parentheses on first use when it is a course-specific
term: `splice site (Spleißstelle)`.

### Epigenetics exception
For the topic **epigenetics**, the handwritten notes are known to be incomplete. Here you
may — and should — **add well-established information beyond the notes** to close gaps.
Any such content MUST be marked:

```markdown
> [!note] Added beyond lecture notes
> Source: general domain knowledge / <citation>. Not from the UHH handwritten notes.
```

For **all other topics**, do not invent content. If something is unreadable or missing,
record it in `wiki/gaps/open-questions.md` instead of guessing.

---

## 2. Directory layout

```
raw/                      # immutable. NEVER edit or delete anything here.
  module1/                # photos/scans of module 1 lecture notes
  module2/                # photos/scans of module 2 lecture notes
  exercises/              # photos/scans of exercise sheets & solutions
  assets/                 # any other images referenced by sources
wiki/                     # LLM-owned. All generated markdown.
  index.md                # catalog of every page (content-oriented)
  log.md                  # append-only chronological record
  overview.md             # the top-level map of both modules
  lectures/               # one page per lecture/session: L01-<slug>.md
  concepts/               # one page per concept/term: <slug>.md
  methods/                # one page per algorithm/method: <slug>.md
  exercises/              # one page per exercise sheet: E01-<slug>.md
  gaps/open-questions.md  # unreadable notes, missing topics, things to verify
CLAUDE.md                 # this schema
```

Naming: lowercase `kebab-case.md` (e.g. `hidden-markov-model.md`,
`needleman-wunsch.md`, `dna-methylation.md`). Lecture/exercise pages are prefixed with a
zero-padded number so they sort chronologically.

Links: Obsidian wikilinks, `[[needleman-wunsch]]`, `[[dna-methylation|DNA methylation]]`.
Link on first mention of a term in every page.

---

## 3. Page formats

Every page starts with YAML frontmatter:

```yaml
---
title: Needleman–Wunsch
type: method            # lecture | concept | method | exercise | overview | gaps
module: 1               # 1 | 2 | both
tags: [alignment, dynamic-programming]
sources: [raw/module1/IMG_0142.jpg]
created: 2026-10-21
updated: 2026-10-21
status: stub            # stub | draft | solid
---
```

### 3.1 Lecture page (`wiki/lectures/L03-sequence-alignment.md`)
```
# L03 — Sequence Alignment
## Scope            one paragraph: what this lecture covered
## Key points       bullets, each linking to the concept/method page
## Diagram          Mermaid overview of the lecture's logic
## Open questions   links into gaps/open-questions.md
## Sources          list of raw/ files this page was built from
```

### 3.2 Concept page (`wiki/concepts/<slug>.md`)
```
# <Concept>
## Definition       1–3 sentences, precise
## Why it matters   biological/computational motivation
## Details          the substance
## Diagram          Mermaid, when it clarifies anything
## Relations        [[see-also]] links, with one line each on *how* they relate
## Appears in       [[L03-...]], [[E02-...]]
## Sources
```

### 3.3 Method page (`wiki/methods/<slug>.md`)
```
# <Method>
## Problem          what it solves, input → output
## Idea             intuition in plain English
## Pseudocode       REQUIRED (see §4)
## Worked example   small, hand-checkable; tables for DP matrices
## Complexity       time and space, with justification
## Variants & pitfalls
## Relations
## Sources
```

### 3.4 Exercise page (`wiki/exercises/E02-<slug>.md`)
```
# E02 — <Topic>
## Task             restated in English
## Approach         which [[method]] applies and why
## Solution         full worked solution, pseudocode where applicable
## Takeaway         the generalizable lesson
## Sources
```

---

## 4. Pseudocode convention

Always a fenced block tagged ```text```. Use 1-based indices unless the lecture used
0-based. `←` for assignment. Comments with `//`.

```text
NEEDLEMAN-WUNSCH(A, B, s, d):
  n ← |A|; m ← |B|
  F[0,0] ← 0
  for i ← 1 to n: F[i,0] ← i · d            // gap penalty down first column
  for j ← 1 to m: F[0,j] ← j · d
  for i ← 1 to n:
    for j ← 1 to m:
      F[i,j] ← max( F[i-1,j-1] + s(A[i], B[j]),
                    F[i-1,j]   + d,
                    F[i,j-1]   + d )
  return F, TRACEBACK(F, A, B)
```

Prefer pseudocode over real code. Add a short Python snippet only when the user asks for
a runnable version.

## 5. Diagram convention

Use Mermaid fenced blocks (```mermaid```) wherever a picture helps: pipelines, regulatory
networks, DP traceback, state machines, hierarchies, timelines.

- `flowchart LR/TD` — pipelines, workflows, decision logic
- `stateDiagram-v2` — HMMs, automata
- `graph` — gene-regulatory / interaction networks
- `sequenceDiagram` — ordered molecular processes
- `classDiagram` / `erDiagram` — data models, file formats

Keep nodes short; put detail in the surrounding text. Every diagram gets one sentence of
caption underneath. Verify the syntax is valid Mermaid before saving.

---

## 6. Operations

### 6.1 Ingest (the user drops a scan into `raw/` and says "ingest it")

1. **Read the image(s)** with the view tool. Transcribe the handwriting carefully.
2. **Report the transcription gist** back to the user and flag anything illegible —
   ask before guessing.
3. **Decide placement**: which lecture/exercise page, which concept and method pages are
   new, which existing pages need updating.
4. **Write/update pages** following §3–§5. A single source typically touches 5–15 pages.
5. **Add cross-links in both directions.** If page A links to B, B's `Relations` or
   `Appears in` must mention A.
6. **Update `wiki/index.md`** — add new pages, revise one-line summaries.
7. **Append to `wiki/log.md`** (see §7).
8. **Record anything unreadable or missing** in `wiki/gaps/open-questions.md`.
9. Default to **one source at a time**, staying conversational. Batch-ingest only when
   explicitly asked.

### 6.2 Query

1. Read `wiki/index.md` first, then drill into the relevant pages.
2. Answer in English with `[[wikilinks]]` as citations back to wiki pages, and
   `raw/...` paths when citing the original notes.
3. **File good answers back into the wiki** as a new concept/method page or a comparison
   page, then update `index.md` and `log.md`. Ask the user first if it is a large new page.

### 6.3 Lint (on request: "lint the wiki")

Check and report, grouped by severity:
- Contradictions between pages.
- Orphan pages (no inbound wikilinks) and dead links (targets that do not exist).
- Terms used repeatedly but having no page of their own.
- Method pages missing pseudocode; process pages that would benefit from a Mermaid diagram.
- Pages still `status: stub`.
- Frontmatter that is missing, malformed, or has a stale `updated` date.
- `index.md` entries that no longer match the files on disk.
- Epigenetics coverage gaps that should be filled per §1.

Propose fixes; apply them only after the user agrees, then log the pass.

---

## 7. index.md and log.md

**`wiki/index.md`** — catalog grouped by `Overview / Lectures / Concepts / Methods /
Exercises / Gaps`. One line per page:

```markdown
- [[needleman-wunsch]] — global pairwise alignment via dynamic programming. *(module 1, solid)*
```

**`wiki/log.md`** — append-only, newest at the bottom. Entries always start with a
parseable header so `grep "^## \[" wiki/log.md | tail -5` works:

```markdown
## [2026-10-21] ingest | raw/module1/IMG_0142.jpg — Sequence alignment
- Created [[needleman-wunsch]], [[smith-waterman]]
- Updated [[L03-sequence-alignment]], [[index]]
- Open question: substitution matrix on p.2 illegible
```

Types: `ingest`, `query`, `lint`, `refactor`.

---

## 8. Hard rules

1. Never modify or delete anything under `raw/`.
2. Never invent course content — except epigenetics (§1), which must be marked.
3. Everything in `wiki/` is English.
4. Every method page has pseudocode; every process gets a Mermaid diagram where it helps.
5. Every ingest updates `index.md` and appends to `log.md`.
6. Cross-links are bidirectional.
7. Ask rather than guess when handwriting is ambiguous.
