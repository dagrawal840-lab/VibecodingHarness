# Multi-model routing

The Parallel step is not "use three tools because three is impressive." Two
lanes is the default. Each
tool gets the job it is best at, fired simultaneously, so no single spinner
costs you the back half of the interview. In a 28-minute UPS-PPPB run, the
build window is roughly 8 minutes. Serial builders spend it watching one
progress bar. Parallel builders spend it talking over three.

## The routing table

| Job | Route to | Why |
|---|---|---|
| Ideation, concept scoring, PRD, prompt writing | Your strongest reasoning model (Claude in this harness) | In a render box every rethink costs a full generation cycle, and the tool starts building before you have chosen. Never ideate there. |
| Fast front-end, polished visual in one shot | Magic Patterns (or v0) | Best screens-per-minute. Fire first; it renders while you talk. |
| Front-end + working logic, state, or a fake backend | Claude Code | The only route that gives you a real interaction to demo, not a picture. |
| A second visual take on the same concept | The other front-end tool | Two takes on your top concept beats one take defended. |

Two rules sit under this table:

- Never ideate inside a prototyping tool. Magic Patterns and v0 are renderers.
  Feed them a finished prompt, not a half-formed idea. Several let you pick
  the model underneath, so that isn't the reason: thinking in the render box
  spends a render cycle per draft and commits the tool to a direction you
  have not chosen yet.
- AI-written prompts are not cheating. Having Claude draft the build prompt is
  the skill being tested. Interviewers score the routing decision and the
  prompt quality, not whether you typed every word.

## The firing order

1. Write the build prompt once, with all four elements (task steps, context,
   desired output, what you do not want). One prompt, adapted per tool, not
   three prompts from scratch. Have Claude write it; you edit.
2. Fire the fastest tool first, then the others. Narrate the routing out loud:
   "Magic Patterns gets the visual because it's fastest; Claude Code gets the
   version with working state." The stated reason is what scores. It is
   evidence for the Parallel sub-dimension of Vibe Coding in
   references/scorecard.md.
3. While tools run, talk through the PRD or backend step. Never watch a spinner
   in silence.
4. When a tool hangs, say so and switch (see references/scripts.md). A hung
   tool costs nothing if you routed in parallel; it costs everything if you
   went serial.

## Worked example: one plausible 8-minute run

Your numbers will differ. Treat this as a shape: two lanes are the
default (one fast visual, one stateful), and a third is a stretch you take only
when you have confirmed the tooling is logged in and working. Before the
interview: log in to each tool, create one empty project in each, and check that
screen share does not break the render. That pre-flight is the difference between
two lanes and zero.

Prompt: "Improve how LinkedIn creators understand who their audience is."
Candidate already spent the earlier minutes opening LinkedIn's analytics tab
(opening the product outscores any framework), picking a top concept
("Audience Pulse," a weekly who-followed-you digest with segment breakdown),
and having Claude draft the four-element build prompt. The 8-minute build
window starts now.

| Min | Action | What the interviewer hears |
|---|---|---|
| 0:00 | Paste the adapted prompt into Magic Patterns. Hit generate. | "Magic Patterns first, it's my fastest renderer. It gets the digest screen: segment cards, follower delta, one insight line." |
| 0:45 | Open Claude Code. Paste the same prompt with the state additions: seeded follower data, a working segment filter, a fake 7-day toggle. | "Claude Code gets the version with working state. I want you to click the 'Engineers at FAANG' segment and see the list actually filter." |
| 1:30 | Both tools running. Switch to the PRD skeleton (assets/prd-template.md). | Talks success metrics: "Primary metric is weekly digest open rate, guardrail is unfollow rate. If this ships and unfollows spike, the digest is guilt-tripping creators." |
| 3:00 | Check Magic Patterns. First render is up but the segment cards show lorem-ish placeholder names. | "Good bones, fake-feeling data. One revision: real segment names like 'Product Managers, 2.1k' and 'Recruiters, 340'." Fires the revision, keeps talking. |
| 4:00 | Check Claude Code. It is mid-build. Do not wait. Cover edge cases from the PRD instead. | "Edge case: a creator with 40 followers. The digest needs a small-audience mode, otherwise every segment is 'other'." |
| 5:00 | Claude Code done. Open concept-audience-pulse.html, click the segment filter live. It works. | "This is the demo: click a segment and the list actually filters. That interaction is the whole concept, and it is the part a screenshot cannot show you." |
| 5:45 | Magic Patterns revision lands. Two takes now exist on the same concept. | "Two versions of Audience Pulse: this one is prettier, this one works. If I had one more cycle I'd merge them." |
| 6:30 | Run taste (skills/taste/SKILL.md) on the winner, out loud. | "One honest critique: the insight line is generic. 'Your audience grew' says nothing. It should say 'PMs overtook engineers as your top segment this week'." |
| 7:15 | Close: restate routing and what shipped. | "Two renderers plus a reasoning lane, one prompt each: two rendered takes and a PRD. The clickable one is what I'd hand to design Monday." |

Notes on the run:

- No wait longer than about 45 seconds went unnarrated. That is the real
  target, not zero waiting.
- Assume one lane runs twice as long as planned. If Claude Code is still
  building at 6:00, stop waiting: present the Magic Patterns take, say "the
  stateful version is still building, I'll come back to it," and come back to
  it. The recovery is the scoreable move, not the flawless cadence.
- The 3:00 revision only worked because the candidate checked early instead of
  waiting for perfect. First render at 3 minutes, revised by 5:45, is normal.
  First check at 6 minutes leaves no revision budget.
- If Claude Code had hung at 5:00, the Magic Patterns take was already on
  screen. That is the entire point of parallel: something renders no matter
  which tool wins.
- Same shape works for a Spotify prompt ("help listeners rediscover old
  favorites"): Magic Patterns gets the Rewind shelf visual, Claude Code gets a
  shelf with a working play-count sort, PRD talk fills the gaps.

## What this looks like from the interviewer's side

Serial builder: one tab, one spinner, dead air. Parallel builder: two tabs
working, a reason for each, and something on screen no matter which tool wins.
Calm beats racing: constant window-switching costs the interviewer the thread
of what they are looking at. Same 8 minutes.
