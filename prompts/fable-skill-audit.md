---
title: Fable Skill Audit
tags: [fable, workflow, critique, claude-code]
source: local
date_added: 2026-07-13
description: Grade every local skill — keep, merge, rewrite, or delete — then fix the three worst descriptions and the worst body.
---

Audit every skill in ~/.claude/skills/.
For each: does the description actually trigger when it should? Does it overlap or collide with another skill? Is it dead weight?

Produce a table: keep / merge / rewrite / delete.
Then rewrite the 3 worst descriptions for trigger accuracy, and fix the single worst SKILL.md body — tighten instructions, remove ambiguity, add the edge cases it currently fumbles.
