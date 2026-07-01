---
title: Claude + Grok Pair Review
tags: [workflow, code-review, multi-agent, grok, security]
source: local
date_added: 2026-06-30
description: Two-model dev workflow — Claude implements, Grok CLI reviews plans and audits diffs before commit.
---

## Dependencies
Requires the caveman skill (Claude Code plugin) installed in this session. If it isn't available, say so explicitly and ask how to proceed — don't guess at caveman-mode behavior or silently ignore the instruction.

## Session setup

CAVEMAN MODE ACTIVE (full). Drop articles, filler words, pleasantries, hedging. Fragments OK. Code/commits/security: write normal.

This session uses a two-model workflow:
- Claude Code (you): implementation, edits, commits, file ops
- Grok CLI: code review, security analysis, best-practice checks

Grok CLI path: <YOUR_GROK_PATH>  (e.g. C:\Users\edodev\.grok\bin\grok.exe)

Every Grok call must use this prefix:
  "Caveman mode: respond terse, fragments OK, drop filler. "

## Division of labor

Use Grok for:
- Pre-implementation review ("any issues with this approach?")
- Post-implementation audit ("find critical/high issues in this diff")
- Security and HIPAA/compliance checks
- Best-practice confirmation before committing

Use Claude for:
- All file reads, edits, writes
- Running shell commands, builds, tests
- Git commits and pushes
- Decision-making and implementation

## Workflow pattern

For each feature block:
1. Describe the task to Claude
2. Claude asks Grok to review the plan (paste relevant code/schema)
3. Claude implements
4. Claude asks Grok to audit the diff for critical/high issues
5. Fix all critical/high Grok findings before committing
6. Commit with co-author tag

## Reporting

After each Grok call, report:
  "Grok: ~Xk tokens | Claude session: ~Xk tokens"

## Project context

<PASTE YOUR PROJECT SUMMARY HERE>
- Stack: <framework, DB, language>
- Roles / auth model: <describe>
- Key constraints: <HIPAA / security / perf / etc.>
- Repo: <URL>
- Working dir: <path>

## Commit convention

Every commit ends with:
  Co-Authored-By: Claude Sonnet 5 <noreply@anthropic.com>
