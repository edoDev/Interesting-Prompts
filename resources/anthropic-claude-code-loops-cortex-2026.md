# From Prompts to Loops: How Anthropic Engineers Achieved 8× Code Output

**Author:** Cortex (@0xCortexl)  
**Originally posted on X:** July 3, 2026  
**Original post:** [https://x.com/i/status/2073074284969295949](https://x.com/i/status/2073074284969295949)  
**Engagement (at time of archive):** 47 likes • 8 reposts • 140 bookmarks • 104.7k views

> *Preserved in personal library for reference and study. Tasteful attribution to the original creator.*

---

Anthropic pays their engineers $80,000 a month. Those engineers now merge 8x more code per day than they did a year ago. Not because the model got smarter. Because they stopped prompting Claude and started building systems that prompt it for them.

Brian Cherny, head of Claude Code at Anthropic:  
> "I don't prompt Claude anymore. I have loops running that prompt Claude and figure out what to do. My job is to write loops."

Most developers read that and have no idea what it means in practice. By the end of this article you will — and you'll have everything you need to build your first one this weekend.

## What a Loop Actually Is

A **prompt** is a single instruction. A **loop** is a goal the AI keeps working toward until it gets there.

The difference is who does the driving. With a prompt you push Claude through every step manually. With a loop you define the goal once and the system runs the full cycle on its own — finding the work, executing it, checking the result and deciding what comes next. All without you in the chair.

Every real loop has five stages.

Three of these do all the real work.

**Verify** is the heart. Without a real check on the result you don't have a loop — you have the agent agreeing with itself on repeat. The check has to be objective. A test that passes or fails. A build that compiles or doesn't. A linter that returns zero or non-zero. Not a second agent asked to "review." Two optimists agreeing is not verification.

**State** is what makes the loop learn. Each pass the AI has to remember what it already tried or it repeats the same mistake forever. A real loop keeps a record outside the conversation — what is done, what failed, what is next. The agent forgets between sessions. The file doesn't.

A **stop condition** is what keeps it sane. A loop with no exit runs until it succeeds, breaks or drains your budget. Every serious loop has two ways to stop — success, and a hard limit. Without this you've built a machine that bills you in silence.

## The 4-Condition Test Before You Build Anything

A loop earns its cost only when all four of these are true. Miss one and keep it as a manual prompt.

**Good first loops** (high objective verifiability, clear stop conditions, repeatable, low risk of silent failure):

**Bad first loops — keep a human in the chair** (open-ended, subjective success criteria, high context drift risk, or one-off creative work):

> *Note: The original X post presents the specific "Good first loops" and "Bad first loops" as curated lists, likely accompanied by visual cards or diagrams.*

## The Five Building Blocks

Every working loop is assembled from five parts. Claude Code ships all five.

### 1. The Automation (the heartbeat)

This is what makes a loop an actual loop and not just a run you did once. A trigger fires on a schedule or event, hands the task to Claude and brings findings back without you going around checking.

The most important is `/goal`. A separate small model checks whether the condition is met — so the agent that wrote the code is not the one grading it.

### 2. Skills (write project knowledge once)

A skill is how you stop re-explaining the same project context every session. A `SKILL.md` file holds the instructions, conventions and rules the loop reads on every run.

Without skills the loop re-derives your entire project from zero every cycle. With skills intent compounds — the conventions, the build steps, the things that went wrong before — written once, read forever.

The automation calls the skill by name. The recurring job stays maintainable instead of rotting inside a schedule nobody updates.

### 3. Sub-agents (keep the maker away from the checker)

The single most useful structural thing in any loop. Split the agent that writes from the agent that checks.

The model that wrote the code is too generous grading its own work. A second agent with different instructions — and sometimes a stronger model — catches what the first one talked itself into.

> One model. Three specialists. The loop runs while you're not watching and the verifier is the only reason you can actually walk away.

### 4. Connectors (so it acts, not suggests)

The difference between a loop that says "here is the fix" and a loop that opens the PR, links the ticket and pings Slack once CI is green.

Without connectors the loop describes what it would do. With connectors it does it.

### 5. The State File (the agent forgets. The file doesn't.)

The piece that sounds too dumb to matter and is the spine of every working loop. A markdown file outside the conversation that records what is done, what failed and what is next.

Tomorrow's run reads this file and resumes. Without it every run restarts from zero.

## What a Real Loop Looks Like

**CI failure triage** — one of the best first loops because verification is automatic and the stakes of bad output are low.

The loop runs:

> *In the morning you wake up to a Slack message, a triage inbox with only the hard problems and a set of PRs that already passed automated review. You didn't prompt a single step.*

> *Note: The original post likely includes a visual diagram or step-by-step breakdown of the CI triage loop execution.*

## The Loop That Compounds Across the Whole Business

The most powerful version is not one loop. It's multiple loops writing to a shared artifact system so they learn from each other.

At SuperDesign their loops cover support, SEO, product growth and ads. Each has its own trigger and workflow. But they all write to the same shared signal store.

The support loop notices five users asking how to export something. It creates a signal.

The SEO loop notices a page with strong traffic but poor conversion. Creates another signal. The product growth loop reads both signals alongside analytics and identifies that the export friction is bigger than the raw data suggested — because now two independent sources confirm the same problem. The ads loop finds a keyword gap and feeds it directly into the SEO loop.

None of these loops are isolated automations. They operate from a shared knowledge base of what the business is learning. Each loop makes every other loop smarter. That's compounding.

## The Failures Nobody Warns You About

**The Ralph Wiggum loop.** An agent meant to signal completion only when finished signals it early. The loop exits on a half-done job and keeps running and billing while producing nothing.  
*Fix:* a hard gate that can objectively fail the work, not a soft "looks good to me."

**Goal drift over long sessions.** Constraints disappear by turn 47 as the context summarizes itself.  
*Fix:* a standing `AGENTS.md` that the agent rereads at the start of every run.

**Comprehension debt.** The faster the loop ships code you didn't write, the larger the gap between what exists and what you understand. The bill that hurts is not the token bill. It's the day you debug a system nobody on the team has read.  
*Fix:* read every diff the loop opens.

**Cognitive surrender.** The pull to stop forming an opinion and accept whatever the loop returns. Designing the loop is the cure when you do it with judgment and the accelerant when you do it to avoid thinking. Same action, opposite result.

**Token costs that compound.** Every loop iteration re-reads the full context and the pile grows each pass. Track cost per accepted change. Below 50% acceptance rate the loop costs more than it saves.

## The Build Order That Actually Works

Everyone who ships loops that survive in production does it the same way:

> Scheduling something you haven't made reliable by hand is exactly how loops blow up while you sleep. Prove it once. Harden it. Then automate it.

The metric that matters is not tokens spent or tasks attempted. It's **cost per accepted change**. If the loop gives you ten results and you reject six you're doing the review work it was supposed to save.

## The Shift That Already Happened

In 2024 the leverage was at the prompt. Better prompt, better output, better developer. In 2026 the leverage is one floor above — the system that decides what Claude works on, when, with what gate and what state survives between runs.

Anthropic engineers merge 8x more code per day not because they found a better way to ask Claude questions. Because they stopped asking questions and started building systems that ask Claude questions on their behalf — continuously, overnight, while they sleep.

The loop doesn't make the work easier. It moves where the work happens. From typing prompts to designing the system that types prompts. From holding the tool to building the factory.

Most developers will keep prompting by hand and wonder why the gap keeps widening. A few will spend one weekend building their first loop — one automation, one skill, one state file, one gate — and never go back.

---

## Attribution & Source

This markdown preserves the full textual content of the original X post by **Cortex (@0xCortexl)**.  

The original post includes additional visual elements (diagrams, lists for good/bad loops, loop execution steps, and the SuperDesign signal example) that are referenced but not fully transcribed here as they were image-based.

**Original X Post:** [https://x.com/i/status/2073074284969295949](https://x.com/i/status/2073074284969295949)  
**Author X Profile:** [https://x.com/0xCortexl](https://x.com/0xCortexl)  
**Archived:** July 4, 2026 for personal library use.

*All credit to the original author for the insights and writing. Shared here under fair use for personal reference and study.*

---

**Tags:** #AI #AgenticSystems #ClaudeCode #Anthropic #PromptEngineering #AIloops #DeveloperProductivity #Automation

*End of archived article.*