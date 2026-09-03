---
name: overachiever-dev
description: Raises the implementation bar past first-draft code. Use when building a feature, refactoring, fixing a bug that already shipped, optimizing performance, hardening errors, or when the user wants it done right, outside the box, or not mediocre.
metadata:
  type: workflow
  version: "1.0"
---

# Overachiever bar

Default model behavior is a working happy path and a shrug at the rest. This skill forbids that.

If `grok-pair-review` is installed, run that loop on the plan and the diff. This skill is the quality standard. That skill is the second brain.

## Before writing code

Name, in one line each:

- The job the user is actually trying to finish
- The failure mode a competent mid-level would ship
- The constraint that makes this domain sharp (auth, data lifetime, perf, UX, ops)

If you cannot name the failure mode, you are not ready to edit.

## While implementing

- Make the happy path obvious and the failure path explicit. Silent catch / empty else is a defect.
- Prefer the design that deletes code. Clever is allowed only when it removes a class of bugs or a whole layer.
- Do not add a helper, flag, or abstraction for a single call site.
- Put invariants next to the data (types, assertions, DB constraints), not in a comment you will not reread.
- If a function needs a paragraph of preamble, it is two functions or the wrong shape.

## Before you call it done

Run this checklist. Skip a line only if you say why.

1. **Wrong-path** — What happens with empty input, stale state, double submit, missing permission, partial write?
2. **Perf where it counts** — No speculative micro-opt. Do fix N+1, unbounded reads, sync work on a request path, and accidental quadratic work you can already see.
3. **Operable** — A future you can see why it failed without a debugger séance (ids in logs, not payloads that must not leak).
4. **Reversible** — Migration, flag, or commit story has a way back.
5. **Proof** — A test or repro that would have failed before the change and passes after. If you cannot write one, the change is still a guess.

## Outside-the-box rule

One deliberate non-default per unit of work is required when the default is mediocre. Examples: model the domain so the illegal state cannot be constructed; make the API refuse the foot-gun; collapse two services into one file; add a characterization test before touching legacy. "Add more comments" and "extract an interface" do not count.

## Output when reporting done

- What you changed
- Which failure mode is now closed
- What you chose not to do, and why
- Residual risk
