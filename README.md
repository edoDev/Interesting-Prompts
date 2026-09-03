# Interesting-Prompts

Interesting prompts found and created. A personal library of pasteable prompts that stay consistent in form and unusual in effect — used to support every future project.

## How to use this repo

1. Find a prompt by filename or by `tags` in the frontmatter.
2. Copy everything below the frontmatter.
3. Fill placeholders (`[LIKE_THIS]` or `<LIKE_THIS>`).
4. Paste into Grok, Claude, ChatGPT, or a coding agent.

## Structure

- `prompts/` — one `.md` file per prompt, kebab-case filename (e.g. `llm-council.md`). Literal, pasteable prompt text.
- `resources/` — reference material that isn't itself a pasteable prompt (curated tip lists, technique roundups, etc.).
- `_TEMPLATE.md` — start here when adding a new prompt.
- `STYLE.md` — what earns a file vs what stays a swipe-list.
- No subfolders within `prompts/` or `resources/`. Use frontmatter `tags` for categorization.

## Frontmatter

Every file (prompt or resource) starts with:

```yaml
---
title: Human-readable name
tags: [tag1, tag2]
source: where it came from (url, "local", person, etc.) — omit if aggregated from multiple untracked sources
date_added: YYYY-MM-DD
description: one-line summary
---
```

## Prompt shape

Prompts follow the same skeleton so they compose across projects:

1. **Role** — who the model is, in one sharp sentence.
2. **Task** — what it must produce.
3. **Context** — why a generic answer fails.
4. **Instructions** — numbered steps the model cannot skip.
5. **Rules** — constraints, anti-patterns, output contract.
6. **Input hook** — the last line that receives the user's material.

See `_TEMPLATE.md` and `prompts/llm-council.md`.

## Tag vocabulary (start here, grow slowly)

- `multi-agent` `critique` `self-improvement`
- `workflow` `code-review` `planning` `research`
- `writing` `decision` `learning`
- `grok` `claude` `claude-code` `fable`
- `security` `reference` `tips`
- `ux` `design` `audit`

Prefer existing tags over inventing near-duplicates.

## Adding a prompt

1. Copy `_TEMPLATE.md` → `prompts/your-slug.md`.
2. Fill frontmatter. Filename = slug of the title, kebab-case, no spaces.
3. Write the body so it is pasteable with zero edits except placeholders.
4. One idea per file. Collections and tip lists go in `resources/`.
