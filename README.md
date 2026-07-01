# Interesting-Prompts
Interesting prompts found and created.

## Structure
- `prompts/` — one `.md` file per prompt, kebab-case filename (e.g. `llm-council.md`). Literal, pasteable prompt text.
- `resources/` — reference material that isn't itself a pasteable prompt (curated tip lists, technique roundups, etc.).
- No subfolders within either. Use frontmatter `tags` for categorization/filtering instead.

## Frontmatter
Each file (prompt or resource) starts with:
```yaml
---
title: Human-readable name
tags: [tag1, tag2]
source: where it came from (url, "local", person, etc.) — omit if aggregated from multiple untracked sources
date_added: YYYY-MM-DD
description: one-line summary
---
```
Content follows after the frontmatter.
