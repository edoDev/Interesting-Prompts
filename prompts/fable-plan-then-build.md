---
title: Fable Plan Then Build
tags: [fable, planning, workflow, claude-code]
source: local
date_added: 2026-07-13
description: Fable maps the repo and writes five executable PLAN files so a cheaper model can implement them.
---

Explore this entire codebase and my open issues/TODOs.
Identify the 5 highest-leverage pieces of work I should do next.
For each, write a separate PLAN-<slug>.md: the goal, exact files to touch, step-by-step order, edge cases a weaker model would miss, and acceptance criteria I can verify.
Write the plans so a less capable model can execute them without asking questions.
Rank the 5 by leverage — tell me which to do first.
