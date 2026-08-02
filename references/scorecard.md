# The scorecard: three areas, seven-dimension evidence

Grade against **three areas**, not the seven UPS-PPPB steps. The seven steps
still generate the evidence. They just stop being the top-level score. Score
each area out of 10, evidence required for every number ("felt strong" is not
a score; quote what the candidate said or did), then close with the single
biggest lever across all three areas.

Timing budget for the full run is ~28 minutes. An area that scored a 9 but
blew its time budget still costs points, visibly, in Time Management.

## The three areas

| Area | What it grades | Sub-evidence (from UPS-PPPB) |
|---|---|---|
| **Product Sense** | Is the user real, is the problem verified, is the solution the right one | User, Problem, Solution, Backend |
| **Vibe Coding** | Can they direct and judge AI output: prompt quality, parallel execution, taste/critique, the rendered result | PRD, Prompt, Parallel (incl. the taste pass) |
| **Time Management** | Budget adherence, recoveries from overruns, whether minutes were spent on what scores | Pacing across all seven steps |

Backend sits under Product Sense here: "a credible path from prototype to a
live test" is a product-judgment question (what would you measure, what would
kill the feature), even though it's asked last.

Final grade = three area scores /10 each + one sentence naming the single
biggest lever across the whole run. Do not average the three into one number;
a candidate who nails Product Sense and Vibe Coding but blows the clock has a
different fix than one who is slow but precise, and a single blended score
hides which.

---

## Product Sense: evidence and calibration

Sub-dimensions: **User** (segments sized with rough %, one or two picked on an
explicit basis, tied to the company's stated mission), **Problem** (opening
the live product and finding specific, verifiable friction instead of theorizing
from memory), **Solution** (five distinct directions, scored, with a stated
pick), **Backend** (a credible path from prototype to a live test, not
stopping at the demo).

Earns points: opening the product before theorizing; a segmentation pick tied
to mission rather than just size; five genuinely distinct directions with visible
scoring; a backend answer with data model, rollout, and a kill criterion.

Loses points: beautiful slow segmentation with no pick; abandoning a bucket
after a redirect without closing it; options with no verdict attached;
stopping at "we'd A/B test it."

### What a 4, 7, and 9 look like

Calibration lines. The examples use a plausible LinkedIn run ("improve job seeking")
and a Spotify run ("help users share music") because those are the two most common
practice prompts in references/question-bank.md.

**User**
- **4**: "The users are job seekers and recruiters." Two buckets, no sizes, no pick.
  Spends 4 minutes describing personas nobody asked for.
- **7**: "Roughly 20% of LinkedIn's ~1B members are active seekers, maybe 5% urgent.
  I'll take urgent seekers." Sized and picked, but the basis for the pick is speed of
  demo rather than mission.
- **9**: "Three buckets: passive browsers (~70%), active seekers (~25%), urgent
  seekers (~5%). I pick urgent seekers: highest pain, and it hits 'economic opportunity
  for every member' most directly. Parking the other two, and if you want me to switch,
  say so now." Sized, picked on mission, buckets explicitly closed, redirect invited.
  Done in under 3 minutes.

**Problem**
- **4**: "Job search filters are probably confusing." Theorized from memory. Zero
  clicks. The interviewer cannot verify anything said.
- **7**: Opens linkedin.com/jobs, clicks around, names one real friction: "Saved
  searches don't surface new matches on the home feed." True, specific, but only one
  finding and no severity ranking.
- **9**: Opens the live product, narrates while clicking: "Three frictions in 90
  seconds. One, applying takes 4 clicks and re-asks for the resume I already uploaded.
  Two, no signal on whether a recruiter viewed the application. Three, saved-search
  alerts arrive by email instead of in-product. The application black hole is the worst:
  it kills return visits. That's my problem." Verifiable, ranked, timestamped by the
  interviewer's own eyes.
- **Recovered-theorizer case**: a strong audit reached only after a coach or
  interviewer pushback caps this sub-dimension at 6 even if the findings
  themselves are excellent tops out at 8: an unprompted audit is what
  earns the 9, and taking a redirect fast and well earns the point back in
  Time Management rather than being penalized twice. Two graders
  should not diverge on this; the cap is the rule.

**Solution**
- **4**: One idea, described at length, never scored against anything. Or five ideas
  that are the same idea at five zoom levels ("dashboard, better dashboard, dashboard
  with AI").
- **7**: Five genuinely distinct directions listed fast, but the pick is asserted:
  "I'll do the status tracker" with no scoring shown.
- **9**: "Five directions: application status tracker, one-click apply with stored
  profile, recruiter-view receipts, AI cover-note generator, interview-prep companion.
  Scoring on impact, effort, and demo-ability in 20 minutes: tracker wins, 9/8/9.
  One-click apply is second but the backend story is weaker. Building the tracker."
  Distinct options, visible scores, stated pick, under 3 minutes. Note: all of this
  happens on paper or in chat. Never ideate inside a prototyping tool.

**Backend**
- **4**: Demo ends, candidate says "and then engineering builds it." No data model,
  no test, no rollout thought.
- **7**: Names the pieces: "status events table, webhook from the ATS, feature flag
  to 5% of urgent seekers." Credible skeleton but no measurement plan attached.
- **9**: A full path to a live test: "Data model: application_events with status
  enum. Source: first-party signals we already hold, recruiter-side status changes
  in the ATS integration plus the member's own application record. I'd start there
  rather than parsing member email, which is a mail-scope and consent program
  measured in quarters rather than a cheap fallback. Sizing: baseline 48h status-check
  rate is about 12%, I want plus 3 points, so roughly 4k members per arm, which is
  5% of urgent seekers for two weeks. Kill criterion: if 48h status-check rate
  does not clear 15%, the black hole wasn't the real problem and we revisit the
  Problem step. If I need the read faster I widen the flag rather than shorten the
  window." A prototype plus a powered, falsifiable test beats a prototype plus
  applause. The sizing sentence is the difference between naming a test and
  naming a tool: a percentage with no baseline, no effect size, and no n is
  astrology.

---

## Vibe Coding: evidence and calibration

Sub-dimensions: **PRD** (goal, non-goals, and a leading/lagging metric split,
all three; non-goals are dropped most often), **Prompt** (all four elements
present: task steps, context, desired output, and what you do not want, and the
candidate can articulate why each is there), **Parallel** (multiple tools
running, with a stated reason for each, plus the taste pass on every render:
does it match the design system, does it use the context, does the copy
sound human, is the hierarchy honest, would the picked segment use it).

Earns points: a tight PRD read aloud in 30 seconds; a prompt whose "what you
do not want" clause is defended on demand; tools fired in parallel with
routing reasons said out loud; a taste pass that catches at least one real
flaw before shipping.

Loses points: any PRD element missing; a strong prompt the candidate cannot
defend; one tool watched serially; an uncritical accept of model output.

### What a 4, 7, and 9 look like

**PRD**
- **4**: A feature list pasted into a doc. No goal, no non-goals, metrics are
  "engagement."
- **7**: Goal and metrics present ("leading: % of applicants who check status within
  48h; lagging: 7-day return rate"), but non-goals missing. Non-goals are the most
  commonly dropped element and the easiest tell of PRD discipline.
- **9**: All three, tight: "Goal: kill the application black hole for urgent seekers.
  Non-goals: no recruiter-side changes, no notification redesign, no mobile in v1.
  Leading metric: % of applicants viewing status within 48h, target 40%. Lagging:
  7-day seeker return rate, +3pts. Guardrail: recruiter response rate flat." Written
  from assets/prd-template.md in ~3 minutes, read aloud in 30 seconds.

**Prompt**
- **4**: "Build me a nice job tracker page." One sentence, zero of the four elements,
  then surprise at the generic output.
- **7**: All four elements present (task steps, context, desired output, what you do
  not want), but when asked "why the do-not-want section?" the candidate shrugs.
  A strong prompt you cannot defend scores like a borrowed one.
- **9**: Four elements present and defended on demand: "Steps so the model builds in
  my order rather than its own. Context is the design-system.md tokens and the urgent-seeker
  persona so the copy isn't generic. Desired output is one self-contained HTML file
  named concept-tracker.html so it renders in one click. Do-not-want bans lorem ipsum,
  'User Name' placeholders, and em dashes, because those are the three fastest ways a
  prototype reads as fake." Using AI to draft this prompt first is fine; see the
  asymmetries below.

**Parallel (execution + taste + rendered result)**
- **4**: One tool, one prompt, four minutes watching a spinner in silence. The
  interviewer watches you watch a progress bar.
- **7**: Two tools running (say, v0 on the tracker UI, Claude drafting the backend
  plan) but no stated reason: the interviewer has to infer the routing logic.
- **9**: "Firing three in parallel: v0 for the tracker screen because it's fastest
  at layout, Claude for a second concept with different information architecture,
  and a chat tab drafting my backend narrative while both render. If v0 stalls past
  two minutes I take Claude's version and move on." Routing per
  references/multi-model-routing.md, reasons said out loud, a fallback pre-declared.
  Dead render time becomes talk time. On the render itself: a taste pass that names
  one true critical thing and fixes or flags it (skills/taste/SKILL.md) is what
  separates a 9 from a 7 here. **The cap, stated once and only here:** no taste
  pass, or a pass whose finding is neither fixed nor flagged out loud, caps
  Parallel at 3 regardless of how good the render looks. Catching a flaw and
  shipping it silently draws the identical cap.

---

## Time Management: evidence and calibration

This area has no seven-step equivalent; grade it directly against the clock.
It answers one question the other two areas can't: did the minutes go where
the points were?

Earns points: hitting the ~28-minute shape (roughly 3/5/3/3/3/8/3 across
User/Problem/Solution/PRD/Prompt/Parallel/Backend); naming an overrun out loud
and self-correcting within a line ("we're at four minutes over on Problem,
moving to Solution now"); stealing time from Problem, never from Parallel,
when behind; a last-minute scope cut stated as a decision ("rather than start
something I can't finish, here's what I'd do from here") instead of a
frantic half-render.

Loses points: silent overruns discovered only when Parallel gets crushed to
two minutes; spending five-plus minutes on harness ceremony before rendering
anything; stealing time from Parallel to protect Problem or Solution (exactly
backwards, since Parallel is where the round is won or lost); reaching the end
with no summary because the clock ran out mid-generation.

### What a 4, 7, and 9 look like

- **4**: Twelve minutes on User and Problem combined, no acknowledgment of the
  overrun, Parallel compressed to three minutes and one tool. The interviewer
  watched the candidate not manage the one resource they were told about.
- **7**: Runs long on Problem by two minutes, notices, says "cutting this
  short to protect the build," but the cut is announced late (minute 11) and
  Prompt gets rushed as a result. Recovery happened; it cost adjacent steps.
- **9**: "We're at four minutes over on the audit, that's enough evidence,
  moving to Solution." Later: "We're at four minutes left; rather than start
  something I can't finish, let me tell you what I'd do from here." Every
  overrun named within a line of happening, every steal taken from Problem or
  PRD, never from Parallel, and a clean verbal close when time runs out.

## Thresholds

Apply per area. Do not average, here or anywhere: the thresholds are stated as
per-area minimums so the three scores stay legible.

- **Not ready:** any area below 6, or two areas below 7. The gap is almost
  always Product Sense's Problem sub-dimension or Vibe Coding's Parallel
  sub-dimension.
- **Passes where this round is being piloted:** no area below 6 and at least
  two areas at 7 or above. Struggles where the round is formalized.
- **Confident pass anywhere running it:** all three areas at 8 or above.

Say the verdict as a decision: "would I advance you, yes
or not yet, and the one thing that decides it." The per-company comparison is a
caveated guess rather than a rubric row; `references/question-bank.md` says plainly
that reported company formats are second-hand and unverified, so a
company-specific bar cannot be scored off them.

When grading a mock run (skills/mock-interview/), score all three areas even if the
run collapsed midway. A collapsed run with an honest 4 on Vibe Coding teaches more
than a polite "incomplete." Route copy and design critiques through
skills/taste/SKILL.md before scoring Vibe Coding; taste findings count as evidence
there.

## The two asymmetries

**Opening the product outscores any framework.** It is the single highest-return action
available and most candidates never do it. A 7 on Product Sense with three verifiable
clicks on Problem beats a 9-worthy framework recited from memory, every time, at every
company running this round.

**Using AI to write your prompt is not penalized.** What is tested is whether you could
have written it yourself, and articulating the four elements demonstrates that faster
than typing it under pressure. The 9-level Prompt evidence above is exactly that
articulation. The 7-level shrug is what actually fails.
