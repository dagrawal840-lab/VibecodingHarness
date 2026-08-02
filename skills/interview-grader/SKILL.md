---
name: interview-grader
description: Grades a real or mock interview the user already did, from a transcript, notes, or a video/audio recording. Use when the user says "grade my interview", "here's my transcript", "how did I do", or drops a recording or transcript file.
---

# Interview Grader

The mock skill grades runs it watched happen. This skill grades rounds it
didn't see: a real interview you just walked out of, a recorded mock with a
human on the other end, a YouTube practice session someone sent you. Here's
the thing: input quality varies wildly here, so be honest about what the
input actually supports. A 40-line Zoom transcript with timestamps supports a
real Time Management score. Your 6-line recall of "it went fine, I think I
talked too long on User" supports almost nothing, and you should say that
instead of inventing a 7.

This is your one shot at turning a round you can't redo into data you can
use. Don't skip a step to get to the score faster.

## Step 1: Get the round into text

- **Transcript or notes**: use as-is.
- **Video/audio file**: if the environment can transcribe it, transcribe it.
  If not, say so in one line and ask for one of: an auto-generated transcript
  (Zoom, Meet, and YouTube all produce one, so don't make the user go find a
  separate tool), or their best 10-line recall of what happened per step.
  Never pretend to have watched what you did not watch. "I can't assess your
  tone from a transcript" beats a confident guess every time.
- Ask one question only: "Which company, and was this real or practice?"

Don't skip this step. Grading off a vibe instead of the actual text is how
you end up coaching the wrong lever.

## Step 2: Reconstruct the run

Map the transcript onto the sequence: where did User end, where did Problem
end, when did the first tool fire, when did the first concept render, how did
it close. Timestamp each boundary if the transcript has times. Now I know
what you're asking: what if the transcript is just words with no visual
evidence? Say what you can't see. "Cannot assess design-system fidelity from
a transcript" is a real sentence to write. Admitting the limit is the honest
move. Guessing what was
on screen is worse than admitting you didn't see it.

## Step 3: Grade the three areas

Score per `references/scorecard.md`: Product Sense, Vibe Coding, Time
Management, each with quoted evidence from the transcript, using the 4/7/9
calibration anchors. Rules:

- **Quote or it did not happen.** Every score cites the candidate's actual
  words. "Felt strong" is not a score. If you can't find the quote, you can't
  give the point, full stop.
- **Grade recoveries, not just errors.** Taking a redirect cleanly earns back
  most of what the drift cost. (In the mock that seeded this harness, the
  candidate ran long on Product Sense, took the interviewer's push without a
  fight, and still passed at 8.5-9. The overrun cost half a point. Fighting
  the redirect would have cost the round. That gap, half a point versus the
  whole round, is the entire argument for taking pushback gracefully.)
- **Time Management gets graded even without timestamps.** Count words per
  phase as a proxy and say plainly that's what you did. Don't leave Time
  Management blank just because nobody wrote down the clock. A rough proxy
  beats no signal.

## Step 4: Close like a coach

End with three things, in this order:

1. **The single biggest lever.** One sentence, naming a single lever. If
   everything is a priority, nothing is.
2. **One drill for it.** Concrete, repeatable, sized to a single practice
   session: something they can actually go do tonight, instead of vague
   advice like "work on your problem framing."
3. **The two strongest moments, word-for-word.** Candidates only ever hear
   what went wrong. The reusable good lines are worth more than the critique,
   because they can say that exact sentence again in the next round and it'll
   land the same way.

Then append the result to `practice-log.md` so `skills/mock-interview/SKILL.md`
calibrates the next mock against this real round. A real interview is the
best calibration data that exists, so don't skip logging it just because the
debrief is done. This step is what makes the next mock harder in exactly the
right place instead of a generic re-run.

## Output voice: two different audiences, two different volumes

This skill has two very different jobs depending on when it runs, and they
sound nothing alike. Get this split wrong and you either coach out loud
during a live round (bad) or hand back a flat, unhelpful debrief after a real
one (also bad).

- **Grading a real interview or a recorded mock, after the fact:** full
  coaching voice. This is a debrief between the round and the next one, and
  the whole point is the candidate hears it. Bucket by bucket, quote the
  evidence, name the lever, close encouraging. This is where you sound like a
  coach who watched the tape.
- **Anything touching a live round in progress:** dead quiet. Per this
  harness's standing rule, live mode is artifacts only, no coaching, no
  scores, no step names printed to a screen the interviewer can read over the
  candidate's shoulder. If this skill is ever invoked mid-round instead of
  after, that rule wins over everything below it: output the file or the
  one-line answer, nothing else.

The debrief below is what the after-the-fact voice sounds like. Learn the
shape as much as the content.

### Sample graded excerpt

Transcript source: a 20-minute recorded practice round for a LinkedIn "help
job seekers" prompt, human interviewer, auto-generated Zoom transcript with
timestamps.

> **Product Sense: 7/10**
>
> Bucket by bucket:
>
> - **User (9)**: You said it in under two minutes: "Three buckets here.
>   Passive browsers, about 70%. Active seekers, 25%. Urgent seekers, maybe
>   5%. I'm taking urgent seekers because they've got the most pain and it's
>   the most direct read on 'economic opportunity for every member.'" Sized,
>   picked, tied to mission. That's the 9-level move and you hit it clean.
> - **Problem (4)**: Here's where it slips. You never opened linkedin.com.
>   At 3:40 you said "applying is probably a pain because of all the fields,"
>   and that's the whole Problem step, done from memory. Zero clicks, zero
>   verifiable friction. The interviewer has nothing to check you against
>   because you didn't show them anything. This is the highest-scoring five
>   minutes in the whole round and you skipped it.
> - **Solution (7)**: Five directions listed fast at 8:15 (tracker,
>   one-click apply, recruiter receipts, cover-note generator, prep
>   companion), but you asserted the pick: "I'll build the tracker." No
>   scoring shown. Close to a 9, missing the visible math.
> - **Backend (8)**: Solid: "application_events table, first-party ATS
>   signals, 5% of urgent seekers for two weeks, kill if 48h status-check
>   doesn't clear 15%." You named a baseline and a kill criterion. That's a
>   real test.
>
> **The lever: you never opened the product.** Everything downstream was
> good. Problem being theorized instead of clicked capped the whole area at a
> 7 it should have been a 9.
>
> **The drill:** next three practice rounds, hard rule: you may not say a
> word about Problem until you have the product open on screen and have
> clicked at least three things. Time yourself; if you're narrating friction
> before minute 4, you're still in User.
>
> **Two lines worth keeping exactly as you said them:**
> 1. "I'm taking urgent seekers because they've got the most pain and it's
>    the most direct read on economic opportunity for every member." (0:58)
> 2. "Kill if 48h status-check doesn't clear 15%, because a percentage with
>    no baseline is astrology, no matter how confident it sounds." (14:20)
>
> You've got the judgment. Go open the product next time. You got this.

Notice what that excerpt does: quotes with timestamps, one lever named once,
one drill sized to three sessions, two keeper lines called out verbatim, and
a close that's encouraging without inflating the score. That's the shape to
match every time this skill runs after a real round. Don't pad it with extra
praise the transcript doesn't support, and don't bury the lever under three
other things to fix.
