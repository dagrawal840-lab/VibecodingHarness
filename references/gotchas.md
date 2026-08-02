# Gotchas

The eight failure patterns. Read before any practice run. Each one has a vignette from a real-feeling run and the one-line save. The saves cross-reference references/scripts.md for verbatim recovery lines and references/scorecard.md for which of the three areas you're bleeding on.

The timing math matters: the round is ~28 minutes of working time. UPS-PPPB budgets 3 on User and 5 on Problem (the canonical 3/5/3/3/3/8/3 shape in references/scorecard.md), and the back half on prototype, presentation, and beyond. Every gotcha below is a way to lose minutes you cannot buy back.

---

**1. The full product sense interview.** The most common way strong candidates lose this round. The work is good; it is the wrong round for it.

*Vignette:* Candidate gets "improve LinkedIn for job seekers." Twelve minutes in, she's still segmenting: active vs. passive seekers, new grads vs. senior ICs, a beautiful 2x2 on the whiteboard. The interviewer glances at the clock. She has 16 minutes left and zero pixels. Her prototype ends up being one screen, half-styled, presented in a rush.

*Save:* "I'll take active senior job seekers and move on. I can revisit if the prototype disproves it." Three minutes on user, five on problem, hard stop. This round scores Product Sense, Vibe Coding, and Time Management (see references/scorecard.md); segmentation past minute 10 scores nothing, and the minutes it eats come straight out of Vibe Coding.

**2. The theorized product.** Describing friction from memory instead of opening the app. Sounds identical to the untrained ear, completely different to an interviewer. Opening the product outscores any framework.

*Vignette:* Candidate on a Spotify prompt: "Discovery is broken, users can't find new music." Interviewer: "Where exactly?" He blanks. He hasn't opened Spotify in the session. Meanwhile the candidate before him opened the app on screen, tapped through Home, and said "three of my first six rows are podcasts I've never played, and my Discover Weekly is buried below the fold." Same thesis. Only one of them has evidence.

*Save:* Open the actual product in the first two minutes, screen-share it, and narrate one specific tap path. "Let me show you rather than tell you" is a scoring line.

**3. The uncritical accept.** Shipping model output without evaluating it. Count the em dashes. Check whether it used the context you gave it.

*Vignette:* Candidate prompts for a recruiter outreach message, gets back "Hi [Name] — I came across your profile and was impressed by your journey!" and pastes it straight into the prototype. Em dash, bracket placeholder, and zero use of the shared-connection data she put in the prompt. The interviewer reads it aloud. Slowly.

*Save:* Before presenting any generated copy, run the taste pass (skills/taste/SKILL.md): one true critical thing, fixed on the spot. "This ignored the mutual-connection context, let me regenerate with it" earns points; silence loses them.

**4. The undefined term.** Building a feature around a concept you never scoped.

*Vignette:* Candidate pitches a "career health score" for LinkedIn and builds a gauge widget showing 72/100. Interviewer: "What's in the score?" Candidate: "Uh, profile completeness, activity... engagement?" Now the whole prototype rests on a number he can't defend, and the follow-up questions eat his presentation time.

*Save:* One line at introduction: "Career health = three weighted inputs: profile freshness, network growth rate, application response rate. Weights are a v2 problem." Scoped in ten seconds, then move.

**5. The serial builder.** One tool, watching it render. Costs you the whole back half.

*Vignette:* Candidate fires one v0 generation and watches the progress spinner for four minutes. It comes back wrong. Second attempt, four more minutes. He's now spent a third of the round producing nothing, single-threaded. The candidate who passed ran v0 on concept one, Claude on the PRD, and drafted concept two's prompt while both cooked.

*Save:* Never watch a render. The moment a generation starts, switch windows and start the next artifact (see references/multi-model-routing.md for the parallel lanes).

**6. The opinion-free menu.** Five concepts, no verdict. A taxonomy without a judgment is a list.

*Vignette:* Candidate presents three rendered concepts: "So we could do A, B, or C. What do you think?" The interviewer thinks: you're supposed to be the PM here. All the build work just converted into a demonstration that this candidate escalates decisions.

*Save:* "Concept B ships first: it needs no new data pipeline and hits the retention metric directly. A is the v2 bet." Recommendation first, reasoning after. This is Product Sense's Solution sub-dimension: five concepts with no pick tops out at a 4 (references/scorecard.md).

**7. The demo that stops at the demo.** No answer for what happens after the prototype.

*Vignette:* Strong build, clean presentation, then: "Great, how would you validate this?" Candidate: "We'd... run an A/B test?" Nothing on metric, cohort, guardrail, or what result kills the feature. The B in UPS-PPPB is Beyond, and it's the cheapest points in the round because it's pure preparation.

*Save:* Pre-load one sentence: "I'd ship to 5% of job seekers, watch application completion rate, guardrail on session time, and I'd size it first: baseline completion is about 12%, I want plus 3 points, that's roughly 4k users per arm, so 5% of job seekers needs two weeks minimum." Thirty seconds, and the sizing sentence is what separates it from naming a tool (assets/prd-template.md has the slot for it).

**8. Ideating inside the prototyping tool.** Every iteration costs a full render cycle, and the tool starts building before you have chosen. Those two costs are the whole reason, regardless of which model is underneath.

*Vignette:* Candidate types "give me feature ideas for Spotify social listening" into the prototyping tool's chat box. It generates one mediocre concept and starts rendering it, unasked. Now she's editing code she didn't want, for an idea she didn't choose, and each rethink costs another render.

*Save:* Never ideate inside a prototyping tool. Generate concepts in your strongest reasoning model, pick one, then hand the prototyping tool a build prompt with all four elements: task steps, context, desired output, and what you do not want. If a prompt is missing one, the harness (CLAUDE.md) will tell you which. And no, having AI write your prompts is not cheating; it's the job.

---

**The pattern under the patterns.** Six of the eight are time thefts in disguise: they feel like diligence and cost you the back half of 28 minutes. The other two (3 and 6) are judgment absences. In practice runs (skills/mock-interview/), log which gotcha you hit each time. Most candidates have a signature one. Fix that one first.
