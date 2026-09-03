---
title: UX Laws — Corrected Card
tags: [reference, ux, design]
source: https://www.instagram.com/reels/DcwkX6OyduT/
date_added: 2026-09-03
description: Reel-style 20-point UX card with mislabeled laws mapped to the real principle and the right design move.
---

Source reel: Adam Hayes, Instagram `DcwkX6OyduT` ("comment UX" lead-gen card). The advice is often usable. Several names are attached to the wrong law. Use this table, not the slide.

Canonical definitions lean on [Laws of UX](https://lawsofux.com/).

| # | Reel name + advice | Verdict | Actual law / heuristic | Design move |
|---|---|---|---|---|
| 1 | Hick's law — reduce choices per screen | Correct | Hick's Law | One primary action. Hide or stage the rest. |
| 2 | Fitts's law — make targets large | Correct, incomplete | Fitts's Law | Frequent actions: large **and** near. Destructive actions: small and far. |
| 3 | Jakob's law — follow familiar patterns | Correct | Jakob's Law | Steal the pattern users already know. Invent only where it is the product. |
| 4 | Law of proximity — group related information | Correct | Law of Proximity (Gestalt) | Related fields share a cluster. Unrelated fields get space. |
| 5 | Miller's law — break content into chunks | Correct direction | Miller's Law + chunking | Group into meaningful chunks. Do not treat "7±2" as a menu-item cap. |
| 6 | Doherty threshold — interactions within 400ms | Correct | Doherty Threshold | Feedback in <400ms. If work takes longer, show progress immediately. |
| 7 | Von Restorff effect — highlight the primary action | Correct | Von Restorff (isolation) | One element may break the visual system. If everything is emphasized, nothing is. |
| 8 | Minimize target distance — place key actions nearby | Duplicate of #2 | Fitts's Law again | Same law. Distance is half of Fitts. Not a separate principle. |
| 9 | Serial position effect — put essentials first | Half | Serial Position Effect | First **and last** items are remembered. Put essentials at both ends, not only the top. |
| 10 | Peak-end rule — end flows memorably | Correct | Peak-End Rule | Design the hardest moment and the last screen. The middle is discounted. |
| 11 | Zeigarnik effect — show real progress | Adjacent | Zeigarnik + Goal-Gradient | Unfinished work stays in memory (Zeigarnik). People speed up near the end (Goal-Gradient). Progress bars serve both. |
| 12 | Law of Prägnanz — simplify complex interfaces | Loose | Law of Prägnanz | People see the simplest stable structure. Reduce visual noise so the structure is obvious. |
| 13 | Law of similarity — use sensible defaults | Wrong name | Law of Similarity ≠ defaults | Similarity: same style = same kind. Defaults belong under Jakob / mental models. |
| 14 | Uniform connected — prevent errors proactively | Wrong name | Uniform Connectedness ≠ error prevention | Connectedness: a shared border/line groups items. Error prevention is Nielsen heuristic #5. |
| 15 | Tesler's law — make errors recoverable | Wrong name | Tesler's Law ≠ undo | Tesler: complexity cannot go below a floor; you choose who holds it. Recoverable errors are Nielsen heuristic #9 (help users recognize, diagnose, recover). |
| 16 | Postel's law — maintain pattern consistency | Wrong name | Postel's Law ≠ consistency | Postel (robustness): be liberal in what you accept, conservative in what you send. Consistency is Jakob + Nielsen #4. |
| 17 | Postel's law — connect related elements visually | Wrong name (and a second Postel) | Uniform Connectedness | This is #14's real job. One name, one job. |
| 18 | Parkinson's law — reduce task completion time | Fair application | Parkinson's Law | Work expands to the time boxed. Shorten the path and the time allowed. |
| 19 | Occam's Razor — reveal complexity gradually | Adjacent | Occam + progressive disclosure | Occam: fewest assumptions. Gradual reveal is progressive disclosure (often how you apply Tesler without dumping complexity on the user). |
| 20 | Pareto principle — make completion feel closer | Wrong name | Pareto ≠ Goal-Gradient | Pareto: 80% of value from 20% of features — cut the long tail. "Feel closer" is Goal-Gradient again. |

## What to keep from the reel

The card is a decent **checklist of design moves**. It is a bad **glossary**. If you paste the raw 20 names into a model, it will audit the wrong things (e.g. "Tesler" as undo, "Pareto" as a progress bar).

Use `prompts/ux-law-audit.md` for reviews. Keep this file as the answer key.
