# Style: consistent form, unusual effect

This library is not a dump of "write me a better email" prompts. Those exist. The point is prompts that change how the model works — councils, pair-reviews, second-brain pipelines, adversarial audits — while staying copy-paste identical in structure.

## Consistency (do not break)

- One prompt per file. Filename is kebab-case. No spaces, no caps.
- Frontmatter always present and complete (`source` may be omitted).
- Body is pasteable. No commentary above the Role heading except frontmatter.
- Sections in this order: Role → Task → Context → Instructions → Rules → Output (optional) → input hook.
- Placeholders: `[SQUARE]` for user facts, `<ANGLE>` for paths/tools that vary by machine.
- Voice of the prompt: direct, no hedge words, no "feel free to."
- Tags come from the vocabulary in README. Add a new tag only when nothing existing fits.

## Innovation (do not flatten)

A prompt earns a file when it does at least one of these:

1. **Changes the model's process**, not just the topic. Multi-voice, staged pipeline, critique-then-rewrite, plan-then-execute.
2. **Names a failure mode** and designs against it (false confidence, missing stakeholders, implementation friction).
3. **Produces an artifact another model or future-you can run** — a plan file, a rewritten answer, a skill, a diff audit.
4. **Has a sharp persona with a job**, not "you are a helpful expert."

Reject prompts that are only:

- A topic swap on a generic template ("explain X like I'm 5").
- A list of 10 tips with no executable text.
- A collection of many small prompts (those belong in `resources/` or get split).

## Quality bar before commit

- Could a weaker model follow this without asking what you meant?
- Is the final deliverable standalone (usable without reading the scratch work)?
- Did you specify what to do when the input is thin or the first pass is already strong?
- Would you actually paste this next week, or only admire it?

## Collections vs prompts

| Goes in `prompts/` | Goes in `resources/` |
|---|---|
| One pasteable prompt | Tip lists, laws, technique roundups |
| Ready to drop into a chat | Notes about prompting |
| Has Role/Task/Context | Has examples, links, commentary |

If you find a list of 60 short prompts, keep it as a resource or split the 3–5 that are actually distinctive.
