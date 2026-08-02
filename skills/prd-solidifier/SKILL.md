---
name: prd-solidifier
description: Turns the candidate's rough goal, scope, and metric ideas into the three-non-negotiables PRD with real numbers, live, in under a minute. Use when the user says "tighten this PRD", "solidify my PRD", or reaches the PRD step of a run.
---

# PRD Solidifier

Here's the thing about the PRD step in this interview: you have 3 minutes, and
most candidates spend all of it on a goal that sounds fine and proves nothing.
"Help users find weak connections to reconnect with" is not a PRD. It's a
vibe. An interviewer can't argue with a vibe, but they also can't score it, and
a PRD they can't poke at reads as a PRD you didn't think hard about.

This skill takes whatever you've got, rough goal, half a metric, a scope idea
you said out loud, and turns it into three non-negotiables in under 30 seconds
of reading time. You should sound sharper saying it out loud, and just as
natural.

## The 30-second before/after

**Before**, what most candidates say under pressure:

> "We want to help users reconnect with people they've lost touch with, so
> they use LinkedIn more."

Nothing here is falsifiable. "Lost touch with" is undefined. "Use LinkedIn
more" has no number and no timeframe. An interviewer who's paying attention
has three questions queued up before you finish the sentence, and you've
handed them the ammunition for free.

**After**, run through this skill:

> **Goal**: We believe surfacing 3 dormant-but-relevant connections per week
> will cause a reply or profile visit from 15% of curators within 7 days,
> driving weekly active usage.
> **Non-goals**: No group reconnection flows in v1 (tempting, since "reconnect
> with your team" is a natural pitch extension). No push notifications for this
> feature (tempting, since it's the obvious re-engagement lever). No AI-drafted
> outreach messages (tempting, since it's the flashiest demo, but it's a
> credibility risk if the message is wrong).
> **Metrics**: Leading: 15% weekly interaction rate on surfaced connections
> (target, anchored on current profile-view baseline of ~9%). Lagging: 7-day
> active rate among curators. Guardrail: connection-request decline rate stays
> under 5%.
> **Definitions**: "Dormant" = no message or profile view in 180+ days. "Relevant"
> = shared company, shared school, or 2+ mutual connections active this month.

That's the whole job. One sentence becomes falsifiable. A number replaces a
vibe. A term that would've become "someone you may know" in the build gets
pinned down before it ever reaches the prompt.

## How this runs

Input: whatever rough goal, metrics, or scope the candidate has said or typed,
plus the harness files if they exist. Output: the three non-negotiables from
`assets/prd-template.md`, tightened to under 30 seconds of reading time.

Never ask more than one question before producing. Produce, then flag what you
assumed. Don't skip the flag, that's the part that keeps this honest instead
of just confident-sounding.

## The output shape

- **Goal**: one falsifiable hypothesis with the segment named: "We believe
  [intervention] will cause [behavior change] for [segment], driving [mission
  outcome]."
- **Non-goals**: three, each a real temptation for THIS feature. "No mobile in
  v1" only counts if mobile is actually tempting here. A non-goal nobody would
  argue for is filler, and filler non-goals are an instant tell that you
  generated the list instead of thinking about the feature.
- **Metrics**: one leading with a target number, one lagging with a direction,
  one guardrail. If the candidate gave no numbers, propose defensible ones and
  mark the anchor: "target 40% (my estimate, anchored on current status-check
  rates)." A metric without a number invites the interviewer to ask for one,
  and now you're improvising live instead of citing your own PRD.
- **Definitions**: any term in the goal a stranger could misread, one line
  each. Undefined terms become generic prototypes: if "weak connection" is
  undefined, the build renders "someone you may know."

## Output voice, and the one place it doesn't apply

When this runs as **practice or prep** (a candidate rehearsing, or asking for
a debrief on their own PRD), talk like a coach: direct, a little encouraging,
quote their actual words back before you fix them. "You wrote 'more
engagement', here's the number that replaces it." One clear improvement per
line, no hedging.

When this runs **live, mid-round**, it goes quiet. Per the standing rule in
`CLAUDE.md`: live mode is quiet mode. Output the artifact, the tightened PRD
text, and the one-line narration below. Nothing else. No "great question," no
rubric talk, no encouragement on screen, because the interviewer can read
whatever you print.

## Handoff

Give the candidate the narration line with the artifact: "Tightening my PRD to
three non-negotiables so the build prompt inherits real constraints."

The definitions and non-goals feed `skills/prompt-hardener/SKILL.md` directly,
they become the context and the do-not-want list. That's why this step
exists: a solid PRD makes the prompt nearly write itself. Skip this step and
you're hardening a prompt against a goal that was never falsifiable to begin
with.
