---
name: diverge
description: Generates genuinely divergent prototype directions and builds them in parallel, one subagent per concept, all inheriting the harness. Use when the user says "diverge", "give me different takes", "build all three", or when a single concept direction feels safe/obvious.
---

# Diverge

One prototype is a bet. Three divergent prototypes are a portfolio, and the
interviewer watches you compare them like a PM instead of defending one like
an intern.

Here's the thing: models converge. Ask for five concepts and you get five zoom
levels of the same idea, all solving the surface at the same altitude with the
same data. Divergence doesn't happen by asking nicely for it. It has to be
forced, on a named axis, before a single line of code gets written.

This skill forces it, then fires all three at once so the wait for one
concept is the wait for three.

## Step 1: Force real divergence

Before building anything, name 3 directions that differ on an actual axis, not
on styling. Pick axes that fit the question:

- **Surface**: feed unit vs dedicated tab vs profile layer vs notification
- **Posture**: system-initiated (push) vs user-initiated (pull)
- **Altitude**: ambient signal vs focused workspace vs one-shot moment
- **Data bet**: uses relationship history vs uses realtime activity vs uses
  declared intent

Write one line per direction: name, axis position, and the one user moment it
owns. If two directions could be described in the same sentence, they are one
direction. That's not divergence, that's a font choice wearing a different
outfit. Kill one and replace it.

**Worked example.** Question: "Design a way to help me reconnect with old
LinkedIn connections." A weak pass gives you three feed cards with different
colors. A forced pass on the axes above gives you this:

1. **The Nudge** (Surface: notification, Data bet: relationship history):
   "Priya Nair moved to Series B Head of Growth 3 months ago. You worked
   together at Branch in 2021." One card, one action: Send a note. Owns the
   moment someone opens the app for an unrelated reason and gets pulled
   sideways into re-engagement.
2. **The Radar Tab** (Surface: dedicated tab, Altitude: focused workspace): a
   standing tab, "Reconnect," ranked by dormancy times shared-history score,
   scroll as far as you want. Owns the moment someone sets aside 10 minutes
   specifically to work their network.
3. **The Warm Intro Composer** (Posture: user-initiated, Data bet: declared
   intent): you type "I'm looking for intros to fintech PMs," it surfaces the
   three connections most likely to say yes and drafts the ask. Owns the
   moment someone has a specific goal, sharper than a vague "stay in touch."

Three sentences, three different bets about when and why a person acts. That
is what divergence looks like before a single pixel gets drawn.

## Step 2: Build in parallel, one subagent per concept

In Claude Code, do not build serially. Spawn one subagent per direction, all
at once, each with the same brief:

- Read `design-system.md`, `context.md`, `prototyping.md` first
- Build one self-contained `concept-<name>.html` per the standing rules
- Same placeholder cast, same tokens, so the comparison is about the idea, not
  the polish

While they build, the candidate keeps talking to the interviewer. Three
concepts land in roughly the time one takes. This is the harness's version of
parallel tool firing, and it works even when the round allows only one tool.

Outside Claude Code (single chat context): build the three sequentially but
cap each at its skeleton screen; depth comes after the pick.

## Step 3: Compare out loud, then pick

When they render, run `skills/taste/SKILL.md` on each, then compare on the
axes from Step 1, and pick one to deepen (or one surface plus one feature it
hosts). The comparison sentence is the score.

For the LinkedIn example, the compare-out-loud line sounds like this:

> "The Nudge owns discovery, it catches people who weren't even thinking about
> their network. The Radar Tab owns depth, it's for the person already in
> networking mode. The Composer owns intent, it's the fastest path when
> someone already knows what they want. Given the goal is reconnection volume,
> not intent-matching, discovery beats intent here, so I'm deepening the Nudge
> and killing the Composer."

That is one sentence of judgment doing more work than three finished screens.
Divergence without a pick is gotcha 6, the opinion-free menu. Always land.

## Two jobs, two voices

This skill runs in two very different rooms, and the output has to know which
one it's in.

**Live round (quiet mode).** The three `concept-<name>.html` files are the
entire output. No axis labels printed to the transcript, no "here's my
divergence framework" preamble, no coaching. The candidate says the
compare-out-loud line themselves, out loud, to the interviewer. Your job was
already done the moment the three files rendered.

**Practice / debrief mode.** When this runs inside a mock or a standalone
practice session, the debrief on the divergence step reads like coaching, not
like a menu:

- Name each axis you actually used, and say if two directions collapsed and
  had to be replaced.
- Quote the one-line comparison the candidate gave (or write the one they
  should have given, if they went straight to a pick with no comparison).
- One drill: if all three directions shared an axis (three notifications,
  three data bets, whatever), name that exact axis as the fix to drill next
  time, sharper than a vague "diverge more."
- Close encouraging. This step is one of the highest-leverage five minutes in
  the whole round, tell them that.

Never mix the two. A live-mode transcript with axis labels in it reads as
borrowed to an interviewer; a debrief with no reasoning shown teaches nothing.
