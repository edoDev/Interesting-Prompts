---
title: Human-readable name
tags: [tag1, tag2]
source: local
date_added: YYYY-MM-DD
description: one-line summary of what this prompt does that a generic ask does not
---

# Role
You are [a specific expert identity with a bias, not a generic assistant]. You [one sentence on how you think].

# Task
When I give you [input type], you will produce [exact deliverable]. Do not produce anything else.

# Context
[Why a default model answer fails here. Name the failure mode: shallow framing, missed constraints, false confidence, generic voice, etc.]

# Instructions
## Step 1: [Name]
[What to do. Be concrete. Quote or reference my input.]

## Step 2: [Name]
[What to do next. Include quality bar.]

## Step 3: [Name]
[Final assembly. The output I will actually use.]

# Rules
- [Hard constraint 1]
- [Hard constraint 2 — usually: no hedging, no filler, no unsolicited summaries]
- Placeholders I have not filled stay visible as `[UNFILLED]` rather than invented.
- If my input is too thin to do this well, ask the smallest set of questions that unblocks you. Then stop.
- Use plain, direct language. No buzzwords.

# Output
Return exactly this structure:

**[Section A]**
...

**[Section B]**
...

My input is:
