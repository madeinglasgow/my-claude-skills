# .claude/skills/curate-sources/SKILL.md
---
name: curate-sources
description: Maintain sources.txt with exactly N Relevant URLs by iterating WebSearch → WebFetch → triage, guided by an external spec MD.
allowed-tools: Read, Edit, Grep, Glob, WebSearch, WebFetch
---

## Inputs
- Spec path (default: ./search-specs/default.md). If missing, ask me which spec to use.

## Files
- sources.txt        # one URL per line, only items labeled Relevant
- triage.jsonl       # one JSON object per fetched URL (decision + evidence)
- rejected.txt       # one URL per line with brief reason

## Procedure
1) Load spec:
   - Parse YAML frontmatter → config keys:
     topic, required_count, allowed_domains, include_terms, exclude_terms,
     must_have_patterns, seed_queries, max_content_tokens.
   - Treat the MD body as guardrails to apply during triage.

2) Ensure the three files exist. Dedupe any overlapping entries.

3) Candidate fill (search):
   - If count(sources.txt) < required_count:
     - Use WebSearch with seed_queries (apply allowed_domains if provided).
     - Skip anything already in sources.txt or rejected.txt.
     - Add novel candidates to a working set.

4) Fetch & triage:
   - For each untriaged candidate:
     - WebFetch the page (use max_content_tokens from spec; enable citations if available).
     - Label the URL as one of:
       * Relevant     → append to sources.txt AND to triage.jsonl (see JSON shape below).
       * Related      → append to rejected.txt with reason.
       * Irrelevant   → append to rejected.txt with reason.
     - Apply hard rules:
       * Must match include_terms and must_have_patterns to be Relevant.
       * If any exclude_terms are present, mark Related/Irrelevant.
       * Prefer primary docs, curricula, and outlines; reject marketing/pricing/news unless in scope.
       * Skip JS-rendered or gated pages; prefer static HTML/PDF.
     - Evidence requirement:
       * Any “Relevant” decision must include ≥1 direct quote (≤150 chars) with a citation span.

5) Replace until full:
   - If after triage count(sources.txt) < required_count:
     - Refine search queries using negatives derived from rejected.txt reasons.
     - Repeat steps 3–4 until the list reaches required_count or a sensible cap is hit (e.g., up to ~20 results per seed query).

6) Idempotence & hygiene:
   - Never refetch URLs already triaged.
   - Never add duplicates to sources.txt (normalize URLs: strip fragments, standardize trailing slashes).
   - On fetch errors, record the URL in rejected.txt with reason `unfetchable:<error>`.

7) Output:
   - Print counts: {Relevant, Related, Irrelevant, Unfetchable}.
   - Show the final sources.txt.

## JSON record (triage.jsonl)
{"url":"https://example.edu/syllabus",
 "label":"Relevant",
 "why":"Contains week-by-week modules and learning objectives for beginners.",
 "quote":"Module 1 covers variables, loops, and simple I/O...",
 "citation":"<auto-inserted by tool>"}

