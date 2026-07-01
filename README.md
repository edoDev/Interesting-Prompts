# Interesting-Prompts
Interesting prompts found and created.

## Structure
- `prompts/` — one `.md` file per prompt, kebab-case filename (e.g. `llm-council.md`).
- No subfolders. Use frontmatter `tags` for categorization/filtering instead.

## Frontmatter
Each prompt file starts with:
```yaml
---
title: Human-readable name
tags: [tag1, tag2]
source: where it came from (url, "local", person, etc.)
date_added: YYYY-MM-DD
description: one-line summary of what the prompt does
---
```
Prompt body follows after the frontmatter.
