# PRD - the 3-minute version

Three non-negotiables (goal, non-goals, metrics), then two inputs your build
prompt needs. Nothing else belongs here. In a 28-minute interview this document
gets 3 minutes, no more. Its only job is to feed your build prompt.
Opening the product outscores any framework, and this
skeleton is short precisely so you have time to open the product.

Where it fits in the UPS-PPPB sequence: you write this in the PRD step, after
Solution, before Prompt. Sections
4 and 5 map directly onto two of the four prompt elements (context, and what
you do not want). If you cannot fill section 5, you have not poked the product
hard enough. Go back.

Timing inside the 3 minutes: 60 seconds on the hypothesis sentence, 30 on
non-goals, 45 on metrics, 45 on definitions and available context. Say the
sections out loud as you type them. Interviewers score narration, see
Time Management in references/scorecard.md.

## 1. Goal and hypothesis
We believe that [intervention] will cause [behavior change] for [segment],
which drives [company's stated mission outcome].

One sentence. If it needs two, your intervention is fuzzy. Weak version:
"We believe reminders will help users stay in touch." Strong version names the
mechanism, the segment, and the company outcome, like the LinkedIn example
below. The difference is what the model can build from.

## 2. Non-goals
We are explicitly not building:
-
-
-

*Non-goals are the fastest of the three sections and the one most often dropped
under time pressure. It is also the one that most clearly demonstrates
judgment.* A good non-goal is something a reasonable PM would build and you are
choosing not to, with an implied reason. "Not building an admin panel" is
filler. "Not auto-sending messages, because a wrong auto-sent message costs
more trust than ten missed reminders" is judgment.

## 3. Metrics

**Leading** (visible in days):
-
-

**Lagging** (visible in quarters):
-

Pick metrics the prototype could plausibly move, then name one guardrail: the
metric you refuse to damage. Saying the guardrail out loud is worth more than a
third leading metric.

## 4. Definitions
Define every fuzzy term before building. If you do not define it, the model
will not use it, and the prototype will produce exactly the generic output you
criticized.

- [term]:
- [term]:

Test for fuzziness: if two PMs would rank the same ten users differently using
your term, define it. "Dormant relationship," "power user," "discovery,"
"engagement" all fail that test until you attach numbers.

## 5. Available context
What data actually exists to personalize this?
-

This section is the anti-generic weapon. Every entry here should appear
verbatim in your build prompt's context element and in the prototype's
placeholder content. A prototype that says "Hi Sarah, you last spoke 14 months
ago at the Stripe offsite" scores; one that says "Hi [Name], it's been a
while!" does not. See skills/taste/SKILL.md for how this gets graded.

---

# Worked example: LinkedIn relationship maintenance

Prompt: "LinkedIn wants to help members maintain professional relationships,
not just accumulate them. Prototype something." Below is the PRD as written in
minute 9 of a real practice run, after 4 minutes poking the LinkedIn app.
Copy the shape, not the content.

## 1. Goal and hypothesis
We believe that a weekly "3 reconnections" digest with a pre-drafted,
context-aware opener for each person will cause members to send 2x more
messages to dormant strong ties, which drives LinkedIn's stated mission of
making members more productive and successful, because career outcomes
(referrals, deals, hires) come disproportionately from dormant strong ties,
not from feed engagement.

## 2. Non-goals
We are explicitly not building:
- Auto-sending. A wrong auto-sent message to a former boss costs more trust
  than ten missed reminders. Human always hits send.
- New-connection suggestions. PYMK already owns accumulation. This is
  maintenance only.
- A relationship CRM with notes, tags, and pipelines. Clay and Dex exist.
  LinkedIn's edge is the data it already has, which a new data-entry surface
  does not add.
- Anything for recruiters or Sales Navigator. Consumer member surface first.

## 3. Metrics

**Leading** (visible in days):
- Digest open-to-send rate: percent of members shown 3 reconnections who send
  at least 1 within 48 hours. Target 15 percent against roughly 4 percent
  organic dormant-tie messaging.
- Draft edit rate: percent of pre-drafted openers edited before send. Want
  30 to 70 percent. Near 0 means people are spamming our words; near 100 means
  the drafts are useless.

**Lagging** (visible in quarters):
- Percent of a member's 1st-degree network messaged in trailing 12 months
  (network liveness, up from a baseline near 8 percent).

**Guardrail:** recipient-side response rate must not fall. If reconnection
messages get answered less than organic ones, we built a spam feature.

## 4. Definitions
- Dormant strong tie: a 1st-degree connection with 3+ past interactions
  (messages, comments, shared employer or school) and zero interactions in the
  last 12 months. Not "someone you haven't talked to," a specific query.
- Context-aware opener: a draft that cites at least one concrete shared fact
  from the graph (last message topic, shared employer era, their recent job
  change). If no fact is available, the person is excluded from the digest.
  Never ship "Hope you're doing well!"
- Reconnection: an outbound message to a dormant strong tie that receives a
  reply within 14 days. The send alone is activity, the reply is the outcome.

## 5. Available context
What data actually exists to personalize this?
- Message history: last thread topic and date per connection.
- Employment overlap: "you both worked at Stripe, 2019 to 2021."
- Their recent activity: job change, work anniversary, post, promotion.
- Mutual connections and shared groups for social proof in the opener.
- Member's own history: which past reconnection drafts they edited or ignored,
  to tune tone over time.

## How this fed the build prompt
Straight lines from PRD to prompt, so you can see the point of each section:
- Section 5 became the context element: the prototype's three cards read
  "Priya Sharma, Stripe 2019-2021, last talked Mar 2025 about her Series A"
  instead of placeholder names. That single move is the difference between a
  4 and a 7 on the Solution sub-dimension of Product Sense in
  references/scorecard.md.
- Section 4's opener definition became the what-you-do-not-want element:
  "no generic greetings, no em dashes, exclude anyone without a concrete
  shared fact."
- Section 2 killed a mid-build temptation to add a "send all 3" button.
  Thirty seconds saved, and a better answer when the interviewer asked
  "why can't I batch these?"

Total time on this PRD: 2 minutes 50 seconds, narrated. Then straight to
Claude to draft the build prompt. Having the model write the prompt from this
PRD is not cheating; it is the job. And none of this ideation happened inside
the prototyping tool. Ideate here, build there. See references/gotchas.md.
