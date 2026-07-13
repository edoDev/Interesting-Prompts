  

# Good prompts for FABLE 

  

## 1 - Plan with Fable, Build with Opus

Fable reads your codebase top to bottom and writes the

roadmap as markdown plans - cheaper Opus 4.8 does the

on-the-ground work.

  

PROMPT for FABLE 5:

Explore this entire codebase and my open issues/TODOs.

Identify the 5 highest-leverage pieces of work I should do

next. For each, write a separate PLAN -< slug>.md: the goal,

exact files to touch, step-by-step order, edge cases a

weaker model would miss, and acceptance criteria I can

verify. Write the plans so a less capable model can execute

them without asking questions. Rank the 5 by leverage - tell

me which to do first.

  

## 2 - build your second brain

Karpathy-style pipeline in Obsidian - knowledge flows

through stages, not topic folders.

  

PROMPT . FABLE 5

 I want a second brain in Obsidian managed by Claude Code - a Karpathy-

style pipeline where knowledge flows through stages, not topic folders:

  

inbox/  zero-friction capture, no organizing

projects/ active WIP, one file per project

output/ shipped artifacts (posts, code)

wiki/  distilled ONLY after something ships

  

Look at **\[my notes dump\]**, then: 1) build the structure with an \_index.md

map in each, 2) write a CLAUDE.md with the conventions + the RULE that

wiki articles are harvested from finished projects, never written

directly, 3) migrate my notes into the right stage, 4) create a /harvest

command. Plain markdown, no plugins.

  

  

  

## 3: AUDIT YOUR LAST 30 DAYS.

  

Point Fable at your session history. It finds what you keep

repeating, what to codify into skills, and where your

prompting leaks.

  

PROMPT . FABLE 5

  

Read my Claude Code session history (~/.claude/projects/

transcripts + history. jsonl). Analyze the last 30 days of how I

actually work: what do I ask for repeatedly? Where do I waste

turns correcting you? Which manual workflows show up 3+ times

that should be a skill or hook? Output: 1) top 5 repeated

patterns with counts, 2) 3 skills you'd create - then create

the best one as a real SKILL.md, 3) the single biggest

inefficiency in how I prompt.

  

  

## 4: FIX YOUR WORST SKILLS.

  

Skills make Claude Code deterministic - the highest-

leverage thing you own. Let the smartest model grade every

one before it leaves.

  

 Audit every skill in ~/.claude/skills/. For each: does the

description actually trigger when it should? Does it overlap

or collide with another skill? Is it dead weight? Produce a

table: keep / merge / rewrite / delete. Then rewrite the 3

worst descriptions for trigger accuracy, and fix the single

worst SKILL.md body - tighten instructions, remove

ambiguity, add the edge cases it currently fumbles.

  

## 5: GO ALL IN: ULTRACODE.

  

Max effort, ~100 sub-agents, adversarial reviews - and this

time Fable executes everything itself.

  

ultracode. Here's the project I've been putting off

because it felt too big: \[describe\]. Break it into phases,

orchestrate subagents for research, implementation, and

adversarial verification, and run it end to end. Don't

stop to ask permission on reversible steps. Verify your

own work before reporting done. I have until tomorrow -

use everything.