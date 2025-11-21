# .claude/skills/generate-search-spec/SKILL.md
---
name: generate-search-spec
description: From a natural-language request, create or overwrite a search spec MD with YAML frontmatter and guardrails for source curation.
allowed-tools: Read, Edit, Grep, Glob, WebSearch
---

## Inputs
- Natural-language request (e.g., “For an intro Agentic AI course for beginners, get 10 sources”).
- Optional inline hints: filename, required_count, preferred or blocked domains.

## Procedure
1) Parse the request. Extract:
   - topic
   - audience/level
   - required_count (default 10)
   - preferred/blocked domains (if any)

2) Synthesize the following fields:
   - seed_queries: 6–12 diverse queries; include site: filters if preferred domains were provided.
   - allowed_domains: derived from request and any explicit hints.
   - include_terms: e.g., syllabus, learning objectives, modules, curriculum.
   - exclude_terms: e.g., pricing, press release, changelog, careers, news.
   - must_have_patterns: a single case-insensitive regex that OR-combines include terms.
   - max_content_tokens: default 35000.

3) Choose a filename:
   - If the user gave one, use it under search-specs/.
   - Otherwise slugify the topic and use search-specs/<slug>.md.

4) Write the spec file exactly in this shape (no extra commentary):

--- 
topic: "<topic>"
required_count: <int>
allowed_domains: [<domain1>, <domain2>]
include_terms: ["syllabus","learning objectives","modules","curriculum"]
exclude_terms: ["pricing","press release","changelog","careers","news"]
must_have_patterns: ["(?i)syllabus|learning objectives|modules|curriculum"]
seed_queries:
  - "<query 1>"
  - "<query 2>"
  - "<query 3>"
  - "<query 4>"
  - "<query 5>"
  - "<query 6>"
max_content_tokens: 35000
---

**Guardrails**
- Prefer primary docs, course outlines, or curriculum pages.
- Reject marketing, pricing, or news pages unless explicitly in scope.
- Require at least one direct quote (≤150 chars) to justify any “Relevant” label.
- Skip JS-rendered or gated pages; prefer static HTML or PDF versions.

5) Print the saved path and a one-line summary of the contents (topic and required_count).

