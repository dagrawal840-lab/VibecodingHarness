# Prototyping Interview Harness

**The complete harness for the PM vibe coding interview.** Drop it into Claude
Code, name a product, and one turn later you have a first-pass design system, a
context library, and standing build instructions (a verified design system once
you attach screenshots). Then it runs you through the round against the clock,
critiques everything you render, and grades you like a hiring manager who
doesn't inflate.

This is your time to shine, and most candidates waste it theorizing instead of
opening the product. Don't be most candidates.

Built from research with hiring managers at Google, Laurel, and DataRobot, 160+
coached candidates, and published candidate reports. Question provenance, source
by source, is in `references/question-bank-research-log.md`; treat everything
tagged `[REAL]` as reported, not confirmed.

## What it can do

| Capability | Where it lives |
|---|---|
| **Build your harness in one turn**: design tokens (real hex values, not "blue"), product context, standing build rules | `skills/interview-harness-builder/` |
| **Brownfield or greenfield**: reads tokens off screenshots of a real product, or designs a system from scratch off a stated anchor product | `skills/interview-harness-builder/` |
| **Run the full mock**: the seven-step UPS-PPPB sequence, timed, with interrupts when you theorize instead of opening the product | `skills/mock-interview/` |
| **Grade you automatically**: three areas (Product Sense, Vibe Coding, Time Management), evidence required, no inflation | `references/scorecard.md` |
| **Taste on demand**: every render gets one true critical thing before you present it: Ship it / One fix / Kill it | `skills/taste/` |
| **Solidify your PRD live**: rough goal in, three non-negotiables with defensible numbers out | `skills/prd-solidifier/` |
| **Harden your prompt**: all four elements, plus the two-sentence defense for when the interviewer asks why it's good | `skills/prompt-hardener/` |
| **Build the backend**: working data layer inside the prototype, events firing in the console, flag rollout with a kill criterion | `skills/backend-builder/` |
| **Diverge on purpose**: three genuinely different concepts, one subagent per concept, fired in parallel so you get three shots instead of one described idea | `skills/diverge/` |
| **Grade a real round**: drop in a transcript or recording of an actual interview and it grades what really happened, then points your next mock at what you fumbled | `skills/interview-grader/` |
| **Extract the real design system**: reads the product's own CSS for exact tokens, and captures its own screenshots when you don't supply any | `skills/design-system/` |
| **Get interview-day ready**: interview-harness-builder ships a clean copy of your setup with practice machinery stripped, plus a preflight checklist | `skills/interview-harness-builder/` |
| **Multi-model routing**: which tool gets which job, fired in parallel, with the stated reason that actually scores | `references/multi-model-routing.md` |
| **Say the right thing under pressure**: 16 scripts for the moments candidates fumble | `references/scripts.md` |
| **Practice for real**: 120-question bank across 12 categories, every question tagged real (with source) or synthetic, each with its hidden trap named | `references/question-bank.md` |
| **Avoid the 8 ways strong candidates lose**: failure patterns from real rounds | `references/gotchas.md` |
| **Quiet in the live round**: artifacts only on screen, no visible coaching while you screen share; guidance exists only in the mock (guided mode, off by default) | `CLAUDE.md` standing rules |
| **Plug into the Job Search OS**: reads your tracker and resume to calibrate mocks, writes scores back next to your applications | `references/job-search-os-integration.md` |
| **Works without Claude**: the core loop compressed into one paste-anywhere prompt | `assets/single-prompt.md` |

## One-turn start (Claude Code)

    cd prototyping-interview-harness
    claude
    /prototyping-interview-harness LinkedIn

That's it. The harness builds your harness, then asks: practice run (clock on) or
live prep (quiet and fast).

Want it in every project? Keep the folder intact and symlink the whole thing,
because every file inside navigates by repo-relative path (`references/gotchas.md`,
`references/scorecard.md`, `assets/prd-template.md`). Copying the nine
sub-skills out on their own dangles all of those references and drops the
dispatcher `SKILL.md` that `/prototyping-interview-harness` resolves to.

    mkdir -p ~/.claude/skills
    ln -s "$PWD" ~/.claude/skills/prototyping-interview-harness

## Claude.ai (web)

Claude.ai takes skills one at a time, so upload the individual skill folders
you want: Settings → Capabilities → Skills → upload each skill folder as its
own zip. Start with `interview-harness-builder`, `mock-interview`, and `taste` if you
only take a few. For graded mocks, also add `references/scorecard.md` and
`references/question-bank.md` to your Project so the skills can pull them.

The full experience (routing, CLAUDE.md standing rules, parallel subagents)
lives in Claude Code. The web version is the travel kit.

## No Claude at all

Open `assets/single-prompt.md`, paste it into any chat model, replace
[PRODUCT], attach 3-5 screenshots. What you get is the core loop: the sequence,
the harness rules, the taste pass, and the grading shape. What it leaves out is
the 120-question bank and its traps, the eight gotchas, the
scripts, and the 4/7/9 calibration anchors. Keep the folder open alongside it.

## Works with any AI coding tool

`AGENTS.md` is the portable copy of the standing rules. Different tools read
different filenames, so point yours at it rather than assuming it gets picked
up. Copy or symlink:

| Tool | File it reads | Do this |
|---|---|---|
| Codex CLI | `AGENTS.md` at the project root | nothing, it is already there |
| Cursor | `.cursor/rules/*.mdc` | `mkdir -p .cursor/rules && cp AGENTS.md .cursor/rules/prototyping-harness.mdc`, add frontmatter with `alwaysApply: true` |
| Gemini CLI | `GEMINI.md` (or set `contextFileName`) | `ln -s AGENTS.md GEMINI.md` |
| Copilot | `.github/copilot-instructions.md` | `mkdir -p .github && cp AGENTS.md .github/copilot-instructions.md` |
| aider | whatever you hand it | `aider --read AGENTS.md` |
| Windsurf, plain chat | nothing automatic | paste `assets/single-prompt.md` |

If a tool silently reads nothing, you get a bare model that sounds confident and
follows none of these rules, which is the worst failure mode here. Check that
the rules loaded by asking it to name the seven steps before you start. Don't
skip this step. A confident model that forgot the rules is worse than no model
at all.

## The map

    prototyping-interview-harness/
    ├── CLAUDE.md                      # the brain: standing rules, loaded every session
    ├── AGENTS.md                      # portable mirror of CLAUDE.md for non-Claude tools
    ├── SKILL.md                       # dispatcher: routes you to the right sub-skill
    ├── skills/
    │   ├── interview-harness-builder/           # the orchestrator: runs the whole build
    │   ├── design-system/             # the extractor: reads the product's real tokens
    │   ├── mock-interview/            # calibrated practice + automatic grading
    │   ├── prd-solidifier/            # rough PRD in, three non-negotiables out
    │   ├── prompt-hardener/           # four elements + the defense
    │   ├── diverge/                   # 3 divergent concepts, one subagent each, parallel
    │   ├── backend-builder/           # data model, live state, events, test plan
    │   ├── taste/                     # the critique pass: nothing ships uncriticized
    │   └── interview-grader/          # grades a real transcript/recording, feeds next mock
    ├── references/
    │   ├── multi-model-routing.md     # which tool gets which job, in parallel
    │   ├── scorecard.md               # the three-area rubric hiring managers use
    │   ├── scripts.md                 # verbatim lines for the moments people fumble
    │   ├── question-bank.md           # 120 practice questions, real vs synthetic tagged
    │   ├── job-search-os-integration.md  # wiring into the Job Search OS
    │   └── gotchas.md                 # the eight failure patterns: read first
    └── assets/
        ├── prd-template.md            # the 3-minute PRD
        └── single-prompt.md           # the core loop in one paste

## The one idea underneath all of it

Opening the product outscores any framework. Everything here exists to get you
from theory to a rendered, on-brand, context-aware prototype faster than the
candidate interviewed before you.

Make it yours: edit `CLAUDE.md`'s standing rules, add your own products to the
question bank, and swap the routing table for the tools you actually use.

## Standalone or plugged in

Every skill here, `diverge/` and `interview-grader/` included, runs standalone.
Point it at a product and go. Drop this folder inside Aakash's Job Search OS
instead and it reads your existing prep (resume, target list, prep tracker) to
calibrate the mock automatically, and `interview-grader/` feeds straight back
into it: grade the real round, aim the next mock at what you fumbled. Nothing
here requires the Job Search OS. It just gets sharper with it.
