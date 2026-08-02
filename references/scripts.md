# Verbatim scripts

The moments people fumble. These are intents to internalize. Read the line,
keep the move, then say it in your own words: a memorized sentence delivered at
an interviewer makes a candidate sound rehearsed. Each one comes with why it
works and what the fumbled version sounds like, so you can hear the miss before
you make it.

Two hard limits, both from watching over-coached candidates lose: **at most two
of these meta-moves per round** (one up-front scope and time statement, one
honest critique at the render), and **never say the number 28 out loud.** The
28-minute budget is the coach's own arithmetic. Keep it out of anything you say
to an interviewer who told you "thirty minutes."

These map onto the UPS-PPPB sequence and the ~28-minute budget in
`skills/mock-interview/`. The scorecard area each script protects is named in
`references/scorecard.md`; the scorecard groups the interview into three areas, down from the seven dimensions you might expect. If a line involves generated copy, `skills/taste/SKILL.md`
still applies: no em dashes, no filler.

---

## Before the clock really starts

**Clarifying the format**
> "Let me make sure I've got the shape of this right. In 30 minutes you want to see me
> prototype, not just describe a solution. Is that right?"

Why it works: it converts an ambiguous prompt into a contract in one sentence, and it signals you have done this before. Interviewers grade format-awareness in the first 90 seconds.
Fumbled version sounds like: "So, um, do you want like a design, or code, or...?" Three vague options, no ownership, and the interviewer now has to manage you.

**Asking why this feature**
> "What's the goal here? Why this versus the other things we could be building?"

Why it works: eight words that surface the interviewer's hidden success metric before you spend a minute building toward the wrong one. A LinkedIn interviewer asking for "a better job alerts experience" is usually testing whether you ask if the goal is engagement or applications. Those are different prototypes.
Fumbled version sounds like: a five-minute unprompted strategy monologue about the market. You answered a question nobody asked and burned a fifth of your build time.

**Using the thinking time**
> "I'll take twenty seconds to pick a segment, then I'll think out loud from there."

Why it works: it uses the offer instead of refusing it, and it shows structure in the same breath. Declining offered thinking time is a reliable way to read as swagger, and the offer is often information: some interviewers are telling you they want to see structure, and a few are watching whether you can be still for thirty seconds. Taking a slice of it costs nothing and buys the segment pick.
Fumbled version sounds like: two minutes of dead air, then a rehearsed framework recital that ignores everything the interviewer said before the silence.

**Setting the time contract**
> "Quick check: is the tool mine to pick, or are we using something on your side? Either
> way, I'll take a few minutes on user and problem, get to building, and flag it if I'm
> running long."

Why it works: the question comes first because in many loops the tool is specified, and announcing your own three-vendor stack to someone who is about to hand you their sandbox reads as not having listened. What survives is the part that pays: a stated split, so every later cut ("skipping the other segments, as I said") is pre-authorized. Keep the tool count to what you can actually run on the machine you are on (see `references/multi-model-routing.md`); two lanes narrated calmly beats three announced and one working.
Fumbled version sounds like: no contract at all, then at minute 22: "oh wow, I didn't realize the time." The interviewer watched you not manage the one resource they told you about.

---

## During problem and prototype

**Opening the product**
> "Before I theorize about what's hard here, can I open the app and walk the real flow?
> I'd rather find friction than guess at it."

Why it works: opening the product outscores any framework. Sixty seconds inside Spotify's actual queue screen yields observations ("the queue is three taps deep and unlabeled") that no whiteboard segmentation can. It also gives your prototype real UI anchors to match.
Fumbled version sounds like: "So if we think about the user journey abstractly..." followed by a persona grid for a product that is open in a tab two clicks away.

**Taking a redirect**
> "Got it, you want me on the hurdles rather than the segments. Let me switch."

Why it works: ten words, zero defensiveness, immediate pivot. Redirects are planted tests of coachability. Scoring rewards the fastest correct response over any defense of your original path.
Fumbled version sounds like: "Right, and that's actually where I was going, because segments feed into hurdles..." You just argued with the hint. That is the sound of the coachability box going unchecked.

**Defining a term**
> "Let me define that, because it'll change what I build."

Why it works: "power user," "activation," "engagement" each have three plausible meanings, and the prototype diverges on which you pick. Defining before building shows you know words become pixels.
Fumbled version sounds like: using "engagement" nine times in four minutes while you and the interviewer silently mean different things, discovered only when the prototype renders the wrong screen.

**When the interviewer hands you the solution**
> "That's a cleaner frame than where I was heading. Let me take it."

Why it works: crediting them and adopting the frame in one breath. Ego costs nothing here; the build was always the deliverable, not authorship of the idea.
Fumbled version sounds like: a grudging "yeah, that's one way to do it" before continuing your original plan. Or worse, silently absorbing their idea and presenting it as yours ten minutes later.

**When you're stuck**
> "Let me say what I'm weighing out loud. I can go deeper on the problem or get to the
> build. Given the time, I think the build is the better use. Tell me if you disagree."

Why it works: it turns a stall into a scoreable prioritization decision and hands the interviewer a cheap way to steer you. Stuck-but-narrating reads as judgment; stuck-and-silent reads as frozen.
Fumbled version sounds like: fifteen seconds of "hmm... let me think... so..." while you scroll your own notes. The interviewer cannot grade what you will not say.

---

## While building

**Kicking off the build (prompt narration)**
> "Watch what goes in this prompt: task steps, the context we just built, the exact
> output I want, and what I don't want: no login flow, no settings page. Those four
> elements are the difference between one shot and five retries."

Why it works: you just taught the interviewer your prompt discipline (the four elements from `CLAUDE.md`) instead of hoping they infer it from a wall of text. The "what I don't want" clause is what actually prevents the tool from building a generic dashboard.
Fumbled version sounds like: typing "make a better notifications page for LinkedIn" and then apologizing to the tool for three regeneration cycles.

**When they ask if AI wrote your prompt**
> "Yeah, Claude drafted it and I cut about a third. Here's the line I added, and why."

Why it works: it answers the literal question in one clause and then shows instead of arguing. This is usually a neutral curiosity question, and meeting it with a rehearsed analogy about calculators is how a candidate reads as defensive. Point at the edit on screen; the edit is the evidence.
Fumbled version sounds like: a sheepish "uh, partially?" that concedes the premise that using the tool well is somehow a shortcut.

**When a tool hangs**
> "This one's hanging. Let me show you the other build while it resolves."

Why it works: this line only exists because you fired tools in parallel at minute six. Note what it does not do: name vendors. The interviewer is not tracking your stack, and product placement mid-demo is noise. Calm plus an instant alternative turns a tool failure into evidence of process. Never ideate inside a prototyping tool; the tool is a renderer, and renderers are replaceable.
Fumbled version sounds like: refreshing the same spinner four times, narrating "it usually doesn't do this," with nothing else running. Now the tool's outage is your outage.

**When the output is wrong**
> "That's not what I asked for, it dropped the empty state. One line fix in the prompt
> rather than re-explaining everything. Watch."

Why it works: diagnosing the miss precisely and patching with a surgical edit shows tool fluency. Regenerating from scratch signals you cannot read your own output.
Fumbled version sounds like: "hmm, weird, let me just try again" followed by the identical prompt and, unsurprisingly, the identical miss.

---

## Closing

**When you're out of time**
> "We're at four minutes. Rather than start something I can't finish, let me tell you
> what I'd do from here."

Why it works: cutting your own scope at minute 24 is prioritization performed live, the same skill the whole interview tests. A crisp verbal roadmap of concept three beats a half-rendered concept three.
Fumbled version sounds like: frantically prompting through the final two minutes, ending mid-generation with "so it would have shown... basically..." and no summary at all.

**Updating your own priors**
> "I thought this would be the strongest concept. Now that I can see it, I don't think
> it is. Here's what changed my mind."

Why it works: this is the whole argument for prototyping said out loud. Rendering changed your judgment; you noticed; you said so. Fire it only when you can point at the pixel that changed your mind, and point at it. Pre-scheduling a mind-change is theater, and an interviewer can hear the difference between "here's what changed my mind" and "here's the part where I say something changed my mind."
Fumbled version sounds like: defending the weakest of three concepts because you pitched it first, while the interviewer stares at the screen that already disproved it.

**Closing with a measurement plan**
> "If we shipped concept two, I'd watch tap-through on the new entry point against the
> current one, with a guardrail on session length. If it doesn't move in two weeks,
> concept three is the fallback."

Why it works: metric, guardrail, timeframe, fallback in two sentences. It ends the interview on the shipping decision, which is where PM interviews are won.
Fumbled version sounds like: "and yeah, so, that's kind of what I built." A shrug where the decision should be.
