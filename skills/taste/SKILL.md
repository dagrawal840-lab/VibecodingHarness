---
name: taste
description: Critiques a prototype, screen, or piece of generated copy before it ships. Use when a concept renders, when the user asks "is this good", or automatically whenever output looks finished. The uncritical accept is the failure this skill exists to prevent.
---

# Taste

Interviewers are not grading whether the model produced something. They are
grading whether you can tell good from adequate. Run this on every rendered
concept and every piece of generated copy before presenting it. On the
three-area rubric (references/scorecard.md), this pass is graded inside Vibe
Coding: it's the evidence for taste/critique of the rendered result. Skipping
it caps that sub-dimension at a 3.

Opening the product outscores any framework. If you can screenshot the real
LinkedIn notification panel, do it before critiquing your fake one. Thirty
seconds of looking at the real thing beats five minutes of remembered rules.

## The 30-second pass

Say one true critical thing, then fix or flag it. Check in this order:

0. **Does it run?** Open the file. Click the primary interaction, the one the
   whole concept rests on. Confirm the console is clean. The most common way an
   AI-generated prototype dies on stage is a JS exception on the first click, in
   front of the interviewer, on the one thing you told them to watch. This check
   costs five seconds and it goes first because a broken demo makes every check
   below irrelevant.
1. **Does it look like the product?** Compare against design-system.md. Wrong
   radius, wrong blue, wrong density all read as pasted-in. Name the worst
   offender. Example: LinkedIn's primary blue is #0A66C2; a #2196F3 button is
   Material design language, and interviewers who work there see it instantly.
   If design-system.md does not exist, do not mark this check N/A: say so out
   loud, compare against known brand facts instead, and flag the comparison as
   unverified. If the artifact is copy with no rendered UI, check voice
   against context.md instead of design-system.md, and still score it.
2. **Does it use the context?** If the harness has relationship or usage data
   and the output is generic, that is a failure regardless of polish. This is
   the exact miss the user should be catching in others' work. "Someone viewed
   your profile" when context.md says the viewer is a recruiter at a company
   the user follows is a wasted signal.
3. **Does the copy sound human, and like this company?** The tells cluster:
   hype verbs ("delve", "leverage", "cutting-edge"), exclamation points, bracket
   placeholders, symmetric sentence pairs, and em dashes (banned in user-facing
   copy, see CLAUDE.md). Voice is the finding; punctuation is one signal inside
   it. Never say the punctuation part out loud in the room. Real names, real numbers, real dates.
   "Jane Doe" and "3 connections" are tells; "Priya Nair" and "12 mutual
   connections, including your former manager" are product.
4. **Is the hierarchy honest?** The most important element should be the most
   visually prominent. If everything is bold, nothing is. One CTA per
   notification. Two equal-weight buttons is a decision you refused to make.
5. **Would the picked segment actually use this?** One sentence: the user from
   the U step opens this screen. What do they do first? If the answer is
   "hunt", the layout failed.
6. **Could the product legally and technically know this?** Specificity is only
   a win if the data exists and is disclosable. Viewer identity, contact details,
   inferred health or employment status, and anything behind a paid or privacy
   gate are permission surfaces to clear before treating them as fields. A prototype that shows data the
   product may not show is worse than a generic one: the follow-up question
   turns your best artifact into a privacy incident. If it is borderline, name
   the guardrail out loud yourself before the interviewer asks.

## Worked example: a flawed LinkedIn notification

Say the mock-interview prompt was "improve job-seeker re-engagement" and your
UPS pass picked the segment "passive job seekers, employed, 2+ years in role."
The model renders this notification concept:

> **You have a new opportunity!**
> A company viewed your profile — they're hiring for roles that leverage your
> skills. Don't miss out on this cutting-edge opportunity to streamline your
> job search!
> [Learn More]  [Dismiss]

Run the pass line by line:

1. **Looks like the product?** Fail. Exclamation points twice; LinkedIn
   notifications almost never use them. The tone reads like a marketing email
   dropped into a feed notification slot. Worst offender: "Don't miss out" urgency framing, which
   LinkedIn reserves for nothing.
2. **Uses the context?** Fail, and this is the concept-level miss. The harness
   knows which company viewed, which role, and that the user has two former
   colleagues there. "A company" throws all of it away. Generic where specific
   was free.
3. **Sounds human?** Fail. "Leverage", "cutting-edge", "streamline" are three
   banned words in two sentences, plus an em dash. No names, no numbers, no
   dates. Nothing here sounds like LinkedIn wrote it.
4. **Honest hierarchy?** Fail. "Learn More" is the vaguest CTA in software.
   And bolding "You have a new opportunity!" spends the emphasis on the least
   informative line.
5. **Would the segment use it?** No. A passive, employed job seeker is
   allergic to hype. This copy reads as spam to exactly the person it targets.
   They archive it in one second.

Five findings, but you name one on camera and fix. The highest-leverage
change is finding 2, because it is the concept, not the polish. Rewrite:

> **3 recruiters from fintech viewed your profile this week**
> Two are at companies where you already know someone. Marcus Webb, from your
> Airtable team, is a mutual at one of them.
> [See who you know there]

Verdict: **One fix.** The judgment to say out loud is the one about the data:
"I kept the companies un-named because viewer identity is permissioned. The
specificity comes from the mutual connection, which we're allowed to show."
That is the sentence a hiring manager scores. The first draft solved
genericness by inventing a disclosure the product may not be able to make,
a more expensive failure than the generic copy it replaced. Total cost:
about 90 seconds of the 28-minute budget, and it should never exceed two.

Note what did NOT trigger Kill it: the underlying concept (profile-view as a
re-engagement hook for passive seekers) was sound. Kill it would apply if,
say, the concept were a daily-streak gamification badge for this segment,
because employed passive seekers do not want a streak. Wrong concept, not
wrong words. Then you say why in one line and fall back to your next-scored
concept from the P step.

## Verdicts

End with exactly one of:

- **Ship it**: present as-is, note the one known weakness out loud.
- **One fix**: name the single highest-leverage change, make it, ship.
- **Kill it**: the concept is wrong at its root. Say why in one line
  and fall back to the next-scored concept. Killing a concept on camera, with
  a reason, scores higher than defending a weak one.

**"One fix" means one edit pass built around a single finding.** You
may bundle multiple corrections into that pass (wrong blue, wrong weight,
placeholder names can all be fixed together) as long as they serve the single
highest-leverage finding you named, but the pass must produce the fixed
artifact. A verdict of "One fix" with no fixed file, or with new product scope
added during the fix (a feature the original didn't have), is not a completed
verdict; make the fix or downgrade to "Ship it, with one flagged weakness."
Ignoring available context is an execution failure (**One fix**) when the
message type itself is right; use **Kill it** only when no version of this
message should exist for this segment.

Never more than one round of fixes per concept during an interview, and the
fix method depends on the lane. If a coding agent produced the artifact, you
have a local file: edit the HTML directly. If a hosted tool (Magic Patterns,
v0) produced it, there is no local file to edit, so send exactly one targeted
follow-up prompt naming the single change and stop there. Same discipline, one
pass either way. Never ideate inside a prototyping tool. Taste under time pressure means knowing
when adequate is enough.
