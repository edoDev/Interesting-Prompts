# Project context template

Copy to the target repo as `.claude/grok-pair.context.md`. The skill re-reads this on every invocation so session-start amnesia cannot drop the facts.

```markdown
# grok-pair context

GROK_BIN: C:\Users\edodev\.grok\bin\grok.exe

Stack:
Auth / roles:
Constraints (HIPAA, PHI, PII, perf, offline, etc.):
Repo:
Working dir:

What Grok must never wave through:
- PHI leaving the approved boundary
- authz checks inferred instead of explicit
- migrations without rollback notes

What "critical" means here:
```
