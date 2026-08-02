---
name: backend-builder
description: Takes a rendered concept past the demo — working data layer inside the prototype, a read-aloud data model, analytics events firing, and a flag rollout with a kill criterion. Use when the user says "build the backend", "make it work", or reaches the Backend step of a run.
---

# Backend Builder

Here's the thing about the Backend step: almost nobody gets here in shape to
do it well, and almost everybody who does it well wins the round on the spot.
Most candidates spend the whole interview on pixels and hand-wave the last
three minutes: "and then this would obviously hit an API." Obviously is not
an answer. The candidates who separate themselves open the console and show
you the event firing.

That's what this skill is for. This is your time to shine. Don't skip this
step.

## The worked example: a LinkedIn reconnect concept

Say the rendered concept is a "Reconnect" card: a stale connection surfaced
with a suggested message, one button, "Send." Here's what that looks like
carried all the way through the four stages.

**1. Data model** (read this aloud in 20 seconds, don't apologize for it
being simple):

```
Connection {
  id: string
  name: string
  lastInteractionAt: date
  mutualContext: string   // "worked together at Acme, 2023"
  strength: enum[cold, warm, active]
}

ReconnectSuggestion {
  connectionId: string
  draftMessage: string
  status: enum[suggested, sent, dismissed]
  suggestedAt: date
}
```

Two tables. That's it. You don't need five for a demo, and reaching for five
is a tell that you're designing for a system you don't have instead of the
prototype in front of you.

**2. Working fake backend.** In the concept HTML, a `connections` array is
already the seed data at the top of the file. Add a `suggestions` object
keyed by `connectionId`. Clicking "Send" mutates `suggestions[id].status` to
`'sent'`, flips the button to a disabled "Sent" state, and writes the whole
object to `localStorage` so a refresh mid-demo doesn't erase the win.

**3. Instrumentation.** Three `console.log` calls, named like they'd appear
in a real analytics dashboard, distinct from debug output:

```js
console.log('reconnect_card_viewed', { connectionId, strength });
console.log('reconnect_message_sent', { connectionId, timeToSendMs });
console.log('reconnect_message_dismissed', { connectionId });
```

Open the console when you say this out loud. `reconnect_message_sent` is
your leading metric. Watching it fire live is worth more than any slide you
could have made about it.

**4. The test plan.** Three sentences: "Roll this to 5% of users with
20+ stale connections for two weeks. Kill criterion: if
`reconnect_message_sent` rate is below 8% of `reconnect_card_viewed` at the
one-week mark, pull it and rework the draft message copy, don't extend the
window. Shipping for real swaps the seed array for a real connections API and
the draft message for the LLM call that's already scoped."

That's a backend. Not a real one. A credible path to one, said out loud in
under a minute. That's what's being graded.

## Why this stage exists

Aakash's take, plainly: the backend step is what will really separate you
from every other candidate in the loop. Most people show up with a pretty
screen and a shrug about what's underneath. You're not going to be one of
them.

## The four stages

Produce in this order, stopping wherever the clock says stop: each stage is
independently presentable. A demo that stops after stage 2 with a working
click still beats a demo that never got past pixels.

1. **Data model**: the 1-3 tables/collections behind the feature, fields and
   types, in a fenced block the candidate can read aloud in 20 seconds.
2. **Working fake backend**: extend the concept HTML with an inline
   `<script>`: state in a JS object, the primary action actually mutating it,
   localStorage persistence if it helps the demo survive a refresh. No
   external requests, no build step. The goal is one interaction the
   interviewer can click that visibly works.
3. **Instrumentation**: the 2-3 events to log, named like real analytics
   events, named descriptively (`reconnect_message_sent` instead of
   `click1`), wired as `console.log`
   calls in the same script so the candidate can open the console and show
   the leading metric firing live.
4. **The test plan**: flag rollout (population, %, duration), the kill
   criterion tied to the leading metric, and what shipping for real would
   swap in (real API, auth, the data source). Three sentences total.

Now I know what you're asking: what if there's no time for all four? Then
stop after whichever stage you finish and say so in one line. A data model
plus a working click beats a rushed, wrong test plan every time. Stop
anywhere. Each stage stands on its own.

## Handoff

Narration line: "The prototype now has a working data layer and logs the
leading metric; here's the flag rollout and the kill criterion."

Rules that hold: tokens from `design-system.md`, definitions from the PRD,
bans from `prototyping.md`. Anything user-facing added here goes through
`skills/taste/SKILL.md` before the candidate presents it. Never produce
something the candidate cannot explain in one follow-up question.

## Two voices, two modes

This skill talks two different ways depending on when it's running, and
mixing them up costs points. Know which one you're in.

**Live mode (during an actual interview round) is quiet mode.** Per
`CLAUDE.md`: artifacts only, minimal words, zero coaching visible on screen.
That means: the data model block, the extended HTML file, the console.log
lines, the three-sentence test plan. Nothing else. No "Bucket by bucket,"
no "you got this," no rubric references. The interviewer is watching the
screen. A visible coach makes every good move look borrowed.

**Debrief/grade mode (practice runs, after a real round)** sounds like
Aakash coaching you after the fact: direct, quoted evidence, one drill,
encouraging close. For example:

> **Backend, bucket by bucket:**
> - Data model: clean, two tables, said aloud in 15 seconds. That's a pass.
> - Working interaction: the "Send" button actually flipped state and
>   persisted. That's the part most candidates skip. You didn't.
> - Instrumentation: you named the event `click_send` instead of
>   `reconnect_message_sent`. An interviewer who's shipped analytics before
>   will clock that as unfinished thinking. Event
>   names are how you prove you know what the leading metric actually is.
> - Test plan: you said "roll it out slowly," no percentage, no duration. Say
>   the number. "5% for two weeks" takes the same three seconds and shows
>   you've sized a flag before.
>
> **One drill:** before your next mock, write the test plan sentence for
> three different features cold, no prototype in front of you. Population,
> percent, duration, kill criterion. Get it to one breath.
>
> You're one rep away from this being automatic. Go get it.

Never let live-mode output carry debrief language, and never let a debrief
go quiet on you. If you're not sure which mode you're in, check whether the
candidate is mid-round or reviewing after: that's the only variable that
matters.
