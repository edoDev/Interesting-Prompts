---
title: Claude Code Workflow Tips (Community Collection)
tags: [reference, workflow, claude-code, tips]
date_added: 2026-06-30
description: Curated list of community-sourced Claude Code workflow suggestions, no literal prompt text — technique summaries + use-case notes only.
---

- **Keep running mistakes.md / buglog file (project-specific error log + fixes)** — Builds project-specific memory; makes subsequent sessions way smarter.
- **Treat Claude Code like senior developer + write full markdown planning doc (feature, behavior, edge cases, files, success criteria) before any code** — Output quality jumps significantly vs. just chatting; catches misunderstandings early.
- **Ask Claude Code to explain what it is about to do before it does it** — Catches ~40% of potential mistakes before code is written.
- **Custom plan-project skill (backlog, user stories, acceptance criteria, architecture, ADR etc.) + implement-project skill with agent team using TDD vertical slices** — Works quite well; "do my job for me" style; ahead of the curve for future common use.
- **Use multiple free AIs to plan/critique ideas back-and-forth before giving task to Claude** — Interesting approach, not commonly seen.
- **Build debuggability/traceability into app (OpenTelemetry, trace IDs, report bug button, plan for tracing)** — Makes it easier/faster for Claude to debug when given feedback.
- **Specific 90% confidence prompt (check files read, ask questions if needed, update project overview before proceeding)** — Produced clear questions + understanding; user was "really happy with the result".
- **Output plan to .md → new chat reviews/pokes holes/improves → repeat 3-4 times** — Don't trust first ideas; cross-check so you can call BS if needed.
- **5-layer memory management system + AI Team (orchestrator + 16 team members) + serving brain** — Highly unorthodox team/agent setup.
- **Detailed spec with checkboxes; have it update as it goes; handoff-ready** — Standard best practice these days; writing spec sometimes takes longer than code.
- **Spec-driven development + handoff every session + use other LLMs for peer review** — Listed as best practices.
- **Ask questions before executing** — Very simple hack, and a very powerful hack.
- **Claude Opus writes handoff document to Claude Code in preferred format + include tests; maintain handover markdown doc (auto-update)** — Avoids memento problems; tests required/included; markdown preferred.
- **Always include comprehensive closeout briefing for next thread + keep context budget under 70%** — Prevents information loss and degradation/hallucination.
- **AI Brain that filters every answer through business/brand DNA** — Stops generic/robotic output; no need to repeat how you work.
- **Use Claude Chat to formulate/tell what to tell Claude Code; ask "What would you recommend?"** — Surprisingly useful results vs. just commands.
- **Give Codex as partner / use Codex to review website developed with Claude** — "Best duo around"; like having 2 assistants.
- **Keep session_context.md (or handover md); start fresh sessions before limit; monitor usage** — Has become a standard best practice.
- **Screenshot cool workflow comment → bring into Claude to implement in your project** — Practical way to adopt others' hacks.
- **Use Claude AI to formulate precise prompts; backlog file + custom skills refined over time** — Returns full report + testing; optimized by urgency.
- **RTFP (Read The F\*\*king Plan); make plan + tell it to make/follow its own plan** — Helpful; can pay for $200 Max plan.
- **Ask: "Did you assume anything? Or would you bet $1000 on it?"** — Prompts careful validation.
- **Swearing + deny exit/planning mode until it confirms intentions (hover stop button)** — Unorthodox control tactic.
- **Prompt: "you are a super duper expert pro coder that makes no mistakes"** — Basic role-prompting.
- **Input is cheaper than output** — Implies plan heavily before heavy output.
- **Knowledge, practice, experiment (ultimate sandbox mindset)** — Try things inside AI; blows mind what's possible.
- **Be explicit with context, break into small steps, iterate instead of all at once** — Standard best practice.
- **Add headless mode; run it yourself to see output and confirm clean** — Helps Claude know everything comes back clean.
- **Use prompts "QA and improve" and "do a dry run"** — Simple QA workflow.
- **Keep library of accepted solutions for common problems with code examples** — Reusable reference.
- **Start small (one thing at a time, e.g. DB access/CRUD)** — Avoid trying to build full turn-key app at once.
- **Get AI to vocalize reasoning + what it thinks you're trying to accomplish before final response** — Cut through bad prompts quickly by interrupting.
- **Voice brainstorm on Claude phone app → download conversation → Claude Code makes detailed spec from it** — Practical for drive-time ideation; results in production-quality code same day.
