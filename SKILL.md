---
name: prototyping-interview-harness
description: Entry point for the Prototyping Interview Harness. Routes to the right sub-skill for a PM vibe coding interview. Use when preparing for or sitting a PM prototyping round, an AI product sense interview, or any interview that asks you to design a feature and take it to a working prototype. Trigger phrases include "prototyping interview", "vibe coding interview", "build the harness", "prep me for a PM interview on <product>".
argument-hint: [target-company-or-product]
---

# Prototyping Interview Harness: dispatcher

Read `CLAUDE.md` in this folder first. It carries the standing rules: interview
mode is the default, the four prompt elements are non-negotiable, and every
prototype ships as one self-contained HTML file. Then route. Your job here is
traffic control. The sub-skills carry the depth, and if you try to wing it
yourself the candidate gets a worse version of what the sub-skill would have
given them. Don't skip the route.

## Routing table

The argument is **the company you are interviewing at**, not the product you
want to practice on. Comfort is the enemy: the harness picks the practice product
from `references/question-bank.md`, and it will not hand you one you know cold
(`skills/mock-interview/SKILL.md`). A named product with no company attached is
read as the harness target, which is a different request.

| Signal | Route |
|---|---|
| No harness exists for the named product | `skills/interview-harness-builder/SKILL.md` |
| "Extract the design system" / "get the real colors" / styling looks off-brand | `skills/design-system/SKILL.md` |
| User wants a mock, practice run, timing, or grading | `skills/mock-interview/SKILL.md` (build the harness first if missing) |
| Output just rendered, or user asks "is this good" | `skills/taste/SKILL.md` |
| "Tighten/solidify my PRD" or the PRD step | `skills/prd-solidifier/SKILL.md` |
| "Harden this prompt" / "is this prompt good" or the Prompt step | `skills/prompt-hardener/SKILL.md` |
| "Build the backend" / "make it work" or the Backend step | `skills/backend-builder/SKILL.md` |
| "Diverge", "give me different takes", "build all three" | `skills/diverge/SKILL.md` |
| User drops a transcript or recording, or says "grade my interview" | `skills/interview-grader/SKILL.md` |
| "Integrate with my job search OS" | `references/job-search-os-integration.md` |
| Choosing which tool builds what, or running tools in parallel | `references/multi-model-routing.md` |
| User fumbled mid-interview and needs a line to say | `references/scripts.md` |
| "What went wrong last time" or pre-run warm-up | `references/gotchas.md` |
| Scoring a finished run | `references/scorecard.md` |

Two of these rows carry an explicit voice split, and it matters:

- **`diverge` is live-mode work.** It fires while the clock is running, so its
  output follows the quiet rule below: three rendered artifacts, no running
  commentary on which concept is "better," no coaching printed to the screen.
- **`interview-grader` is post-mode work.** The round is over, nobody is
  screen sharing, so the debrief gets the full coaching voice: bucket by
  bucket, quoted evidence from the transcript, one drill, an encouraging
  close. Don't quiet that one down. It's the one place in this harness where
  you're allowed to sound like a coach instead of a tool.

## Example utterances → routes

1. "Prep me for a prototyping interview at LinkedIn." → interview-harness-builder.
   No harness exists yet, so build `design-system.md`, `context.md`, and
   `prototyping.md` for LinkedIn (brownfield: pull tokens from screenshots),
   confirm in one line, then ask: practice run or live prep?
2. "Run me through a timed mock on Spotify. 30 minutes on the clock." →
   mock-interview. Check for a Spotify harness first; if absent, build it
   silently, then start the ~28-minute UPS-PPPB sequence and grade against the
   three-area scorecard (Product Sense, Vibe Coding, Time Management).
3. "Here's the concept file, just rendered. Would this pass?" → taste.
   Say one true critical thing before anything else. Do not grade the whole
   run; that is mock-interview's job.
4. "Should I fire v0 or Claude for the settings screen while Lovable does the
   feed?" → multi-model-routing. Tool selection and parallelism questions
   never go to interview-harness-builder.
5. "The interviewer just redirected me from creators to recruiters and I froze."
   → scripts.md for the verbatim recovery line, then back to mock-interview if
   a run is in progress. Closing the abandoned segment out loud is worth points
   on the User sub-dimension of Product Sense.
6. "Give me three different takes on the feed redesign, build all three." →
   diverge. Force real divergence (not three shades of the same idea), fire
   one subagent per concept, stay quiet while they render.
7. "Here's the recording from my Notion interview yesterday, grade it." →
   interview-grader. It never saw the round live, so it works from the
   transcript alone, then feeds what it finds into the next mock's difficulty.

## Ambiguity rules

- Product name plus nothing else → default flow below. Never open a
  prototyping tool to ideate; ideation happens in text, on the clock.
- Two signals at once (e.g. "mock me on Notion" with no harness) → harness
  first, then the requested skill. Harness absence always wins the tiebreak.
- Mid-mock, any critique request stays inside mock-interview. Taste is for
  standalone review, once the timed run is over.

## Default flow (invoked with just a product name)

Build the harness, confirm in one line ("Harness ready for <product>: 3 files,
brownfield"), then ask whether this is a practice run (start the clock,
mock-interview owns pacing) or live prep (stay quiet, answer in one or two
lines, speed over polish). Remember the core asymmetry from the scorecard:
opening the live product outscores any framework, and an AI-written prompt is
fine as long as all four elements are there and defensible.
