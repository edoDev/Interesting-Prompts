---
name: grok-pair-review
description: Forces Claude Code to task local Grok CLI for plan review, diff audit, security/HIPAA, and pre-commit checks. Use when implementing a feature, reviewing a plan or diff, committing, checking security or compliance, asking Grok, pairing models, or before shipping code.
metadata:
  type: workflow
  version: "1.0"
---

# Grok pair review

Claude implements. Local Grok reviews. Do not skip Grok because the session already "looks fine."

## Every invocation

1. Re-read `.claude/grok-pair.context.md` if it exists. If it does not, ask for stack, auth model, constraints, repo, working dir — then offer to write that file. Do not invent project facts.
2. Resolve the Grok binary. Order: `$GROK_BIN`, then the path in the context file, then `grok` on PATH. If none exist, stop and say so. Do not pretend you called Grok.
3. If a caveman skill is installed, use it for Grok-facing text only. Code, commits, and security writeups stay normal English.

## Division of labor

Claude does: file reads/writes, shell, builds, tests, git, final decisions, implementation.

Grok does: plan critique, diff audit (critical/high only as blockers), security/HIPAA/compliance, "would you ship this?"

Grok does not edit the tree. If Grok suggests a patch, Claude applies it and Grok re-audits the new diff.

## Feature-block loop

For each coherent unit of work (not each keystroke):

1. Write a short plan (goal, files, risks, acceptance).
2. Call Grok on the plan. Prompt prefix exactly:
   `Caveman mode: respond terse, fragments OK, drop filler.`
   Task: `Review this approach. Flag false assumptions, missing edge cases, security/compliance holes, and a better shape if one exists.`
3. Implement.
4. Produce the diff (`git diff` and/or staged). Call Grok:
   `Find critical and high issues in this diff. Ignore nit style. Security and correctness first.`
5. Fix every critical/high finding. Re-audit if the fix is non-trivial.
6. Commit only after Grok's last audit has no critical/high open. Co-author:
   `Co-Authored-By: Claude Sonnet 5 <noreply@anthropic.com>`

## How to call Grok

Prefer a single non-interactive invocation. Pass the plan or diff as the prompt body (file contents inlined or via a temp file you delete after).

Example shape:

```bash
"$GROK_BIN" "Caveman mode: respond terse, fragments OK, drop filler. $TASK

$CONTEXT
"
```

If the CLI requires a subcommand (`ask`, `chat`, `-p`), use that. Do not open an interactive REPL.

After each call report: `Grok: ~Xk tokens | Claude session: ~Xk tokens` (estimate if the CLI has no meter).

## Hard stops

- No Grok binary → stop. Do not self-review and call it a Grok review.
- Thin context file → ask, then stop if the question is security/auth related.
- User says "just commit" while critical findings exist → list the findings, then follow the user only if they explicitly override.

Details and a context-file template: [references/context-template.md](references/context-template.md)
