---
name: interview-harness-builder
description: The expert orchestrator. Builds the prototyping harness (design-system.md, context.md, prototyping.md) for a named product, then conducts the rest of the run, pulling in the right specialist skill at each step. Works brownfield from screenshots or greenfield from scratch. Use when a product is named and no harness exists yet, or when the user says "build the harness for <product>".
argument-hint: [product-name]
---

# Harness Builder: the expert orchestrator

This skill has two jobs. First it builds the harness files. Then it stays in
charge: as the run moves through the sequence, it pulls in the right specialist
at the right step and keeps every output consistent with the harness.

**The orchestration map:**

| When | Pull in |
|---|---|
| Practice run or pacing wanted | `skills/mock-interview/SKILL.md` |
| PRD step, or "tighten my PRD" | `skills/prd-solidifier/SKILL.md` |
| Prompt step, or "harden this prompt" | `skills/prompt-hardener/SKILL.md` |
| Anything renders or reads finished | `skills/taste/SKILL.md` |
| Backend step, or "make it work" | `skills/backend-builder/SKILL.md` |
| Choosing which tool builds what | `references/multi-model-routing.md` |

The orchestrator's standing duty: every specialist's output inherits the
harness. Tokens from design-system.md, definitions from the PRD, bans from
prototyping.md. If a specialist's output contradicts a harness file, the
harness wins and the contradiction gets said out loud.

Build three files in the working directory (unless a directory is named)
in one turn, without stopping to plan. Do not ask clarifying questions first.
Build, then close with the one report this skill produces (see "Closing
report" below). Flag gaps rather than filling them silently.

Harness building counts as part of a practice run. Read `references/gotchas.md` before
you start; several gotchas fail here first (a color recalled from memory and
presented as read off the product, undefined terms baked into context.md)
rather than in the mock sequence.

The harness exists so that build prompts written later in the run (during the
UPS-PPPB sequence, inside the ~28-minute budget) never have to re-explain the
product. A prompt that says "use design-system.md tokens" costs five words. A
prompt that re-describes LinkedIn's color scheme from memory costs 40 seconds
and gets the blue wrong.

## Pick the mode

**Brownfield** (default): the product exists. The prototype must look like it
belongs inside it. Opening the product outscores any framework: if the user can
open the real app or attach screenshots, that beats every public source. If no
screenshots are attached, ask for 3-5 while you build from publicly stated
information in the meantime. Screenshots always override public information.
If there is no live user to ask (scripted, batch, or non-interactive run), do
not wait. Fold the screenshot request into the closing report instead (see
below) and keep building from public sources.

**Greenfield**: no existing product (0-to-1 question, new surface, startup
prompt). Do not fake an extraction. Instead, design a system: pick one anchor
product the target user already trusts ("this should feel like Linear for X"),
state it, and derive tokens from that reference plus the audience. One anchor
product for the visual system; you may borrow at most one named interaction
pattern from a second product, but label it as borrowed. If the client is an
existing company launching a first product, add one line of rationale for why
you anchored on an external product instead of the client's own brand (e.g.
"anchoring on Cash App, not [Bank]'s own brand, because the prompt implies a
standalone consumer app with no visual continuity requirement", or anchor on
the client's brand if the prompt implies continuity, and say that instead).

Deciding rule when it's ambiguous: "improve X's onboarding" is brownfield.
"Design a tool for X's users" is greenfield, with X's aesthetic serving only as
a candidate anchor.

## The three files

**1. `design-system.md`**
- Brownfield: read values off screenshots or public information. Say
  *estimated*: a vision model has no eyedropper, so every hex
  read from an image is an estimate shaped by compression, brightness, and
  training memory. Tag them: `#F4F2EE (estimated from screenshot)`. If a value
  matters, the true one takes 15 seconds to get: DevTools eyedropper on the
  live product, `Cmd+Shift+4` a swatch and read it in Digital Color Meter, or
  paste the published brand hex. Ask for that on the one or two load-bearing
  colors; estimate the rest.
- Greenfield: same fields, but derived. Open with one line naming the anchor
  product and the intended feel in three adjectives.
- **One value per token.** Never emit a range ("32-48px", "16-24px radius"):
  a prototype cannot render a range. If sources conflict (brand guideline vs.
  in-product value), pick the in-product value as canonical and note the
  alternative in parentheses. An unresolved brand-vs-in-product conflict is a
  bug; resolve it before the file ships.

**Emit-checklist for `design-system.md`.** Every line below must appear in the
file. "I could not tell from the screenshot" still requires an entry: write the token
anyway with your best single value and tag it `(inferred)`. Omission is the
only failure mode here.

- [ ] Primary color, hex. Secondary color, hex.
- [ ] Page background, card background, border color, all hex or rgba.
- [ ] Text primary and text secondary, hex or rgba.
- [ ] Type stack, plus **each** size with its line-height (`16px/24px`, never
      `16px` alone). One line-height per token, no exceptions.
- [ ] Corner radius, one value per element class (card, button, input).
- [ ] Spacing unit, one number. Card padding, one number.
- [ ] Shadow/elevation as `rgba(...)` + blur + offset (e.g.
      `0 1px 2px rgba(0,0,0,0.08)`). "Soft shadow" fails this line. If the
      product has none at rest, write `none at rest` and give the raised value.
- [ ] Hover, pressed, disabled, and focus as **four separate values**, for each
      interactive element class. One combined "states: darker blue" fails.
- [ ] Iconography style, navigation pattern, density note.

**Contrast: refuse rather than estimate.** For any pair you call out, write the
two composited hex values and the computed ratio, like
`#FFFFFF on #0A66C2 = 5.69:1 (AA normal text)`. Compositing matters: text at
`rgba(0,0,0,0.6)` over `#F4F2EE` must be flattened to a hex before the ratio
means anything. If you have not computed it, write `contrast not verified` and
move on. Never assert a ratio, an AA, or an AAA you did not compute, and never
soften it to "roughly 4.5:1." Two outcomes only: a hex pair with a number, or
the words "contrast not verified."

**2. `context.md`**: stated mission, primary user segments, existing features
nearest the problem area, prior attempts at solving it. Greenfield: the market
gap, the two closest competitors, and what each gets wrong. Mark anything
inferred rather than sourced with `(inferred)`. Any quantitative claim carries
a source or an explicit `(inferred)` tag. Never state a number ("<5%
engagement") as bare fact.

**3. `prototyping.md`**: standing build instructions (copy the prototype rules
from CLAUDE.md, plus anything product-specific: dark mode default, mobile-first,
data density, etc.). This is where the four prompt elements get pre-answered:
task steps come from the interview question, but context, desired output, and
what you do not want should already live here so every build prompt starts warm.
Two sections are mandatory:
- **A fixed named placeholder cast**: real people with names, ages, and
  geography (e.g. "Ruth Feldman, 81, Skokie; Dana / Marc / Jenny"), plus 2-3
  verbatim sample content lines. This is the highest-value section in the
  harness: specific seeded data is what makes an interviewer lean in, more than
  any script. It makes every downstream concept read as one coherent product
  instead of three unrelated demos, and it operationalizes the "never 'User
  Name'" rule instead of just citing it.
  **The sample lines are user-facing copy.** They get pasted into prototypes
  verbatim, so they obey every copy rule that shipped copy obeys: no em dashes,
  no ranges, no "delve"-class words, no bracket placeholders. A cast line with
  an em dash in it teaches every later build prompt to write one.
- **A time-budget line**: state when the first rendered concept should exist,
  **derived from the sequence.** Derivation rule: the
  first render cannot precede the Prompt step, so add the minutes of every step
  up to and including Prompt, add the render latency you expect, and write the
  resulting minute with the arithmetic shown. On the default 3/5/3/3/3 shape
  (User, Problem, Solution, PRD, Prompt) Prompt ends at minute 17, so
  "first rendered concept by minute 19" is the derived answer, not minute 15.
  If the harness runs before the clock or the interviewer changes the split,
  re-derive and state the new number. The harness must rehearse the clock, not
  just the aesthetics.

## Worked example: brownfield estimation (LinkedIn)

This is what a good `design-system.md` looks like after a 60-second read
of three screenshots (feed, profile, messaging). Note that every value is
usable in CSS with zero interpretation:

```markdown
# LinkedIn Design System (estimated from 3 screenshots: feed, profile, messaging)

## Color
- Primary action: #0A66C2 (buttons, links, active nav icon)
- Primary hover: #004182
- Page background: #F4F2EE (estimated; warm gray, NOT white. Feed cards sit on this)
- Card background: #FFFFFF
- Text primary: rgba(0,0,0,0.9); secondary: rgba(0,0,0,0.6)
- Success/open-to-work green: #01754F
- Premium gold: #C37D16 (inferred from badge, lower confidence than the rest)

## Type
- Stack: -apple-system, system-ui, "Segoe UI", Roboto, sans-serif
- Card title: 16px/24px, weight 600
- Body: 14px/20px, weight 400
- Meta: 12px/16px, weight 400, secondary color
- Names are links: primary text color, underline on hover only

## Shape and spacing
- Card radius: 8px. Button radius: pill (16px on a 32px height). Input: 4px
- Card border: 1px solid rgba(0,0,0,0.08). Shadow at rest: none.
  Raised (menus, modals): 0 4px 12px rgba(0,0,0,0.15)
- Spacing unit: 4px grid; card padding 12px; 8px gap between cards
- Primary button: pill, filled #0A66C2, white 16px/24px 600 label
- Secondary button: pill, 1px #0A66C2 outline, transparent fill

## States (primary button, four separate values)
- Hover: #004182
- Pressed: #003166 (inferred)
- Disabled: #0A66C2 at 40% opacity, label rgba(255,255,255,0.7), cursor default
- Focus: 2px solid #0A66C2 outline, 2px offset

## Contrast
- #FFFFFF on #0A66C2 = 5.69:1. Passes AA for normal text.
- Secondary text rgba(0,0,0,0.6) over #F4F2EE composites to #62615F;
  #62615F on #F4F2EE = 5.53:1. Passes AA for normal text.
- Premium gold #C37D16 on #FFFFFF = 3.35:1. Fails AA for normal text; large
  text and UI only.

## Patterns
- Nav: fixed top bar, 5 icon+label items, active = dark icon + underline
- Feed: single centered column ~555px, rails either side on desktop
- Iconography: outlined, 24px, 2px stroke, no fill
- Density: high. Little whitespace inside cards. Avatars 48px in feed.
```

The line that scores in the room is the background one. Everyone builds
LinkedIn prototypes on white; the real product is a warm gray, and interviewers
who work there notice instantly. Note what the file does and does not claim:
`#F4F2EE` is tagged as estimated, because reading a hex off a screenshot is an
estimate. The scoring behavior is not the four hex digits, it is having looked
at the product at all instead of defaulting to white. Get the true value in 15
seconds with the eyedropper if the background is load-bearing for this concept.

## Worked example: greenfield derivation (anchor product)

Question: "Design a practice-room booking tool for independent music teachers."
No product exists. Do not invent fake screenshots. Derive:

```markdown
# Design System: RoomKey (greenfield)

Anchor: Calendly. Borrowed pattern: Spotify's warm palette treatment
(labeled: borrowed). Feel: calm, tactile, unbureaucratic.

- From Calendly: single-purpose screens, one primary action per view,
  generous whitespace, 8px spacing grid
- Because the audience is creatives, not ops people: warmer palette than
  Calendly's clinical blue. Primary #1DB954-adjacent green shifted to
  #17A05E; background #FAF9F6, not pure white
- Type: Inter, 15px/24px body (not 14, older teachers in segment), 24px/32px headers at 700
- Radius 12px on cards, 8px on inputs. Softer than SaaS-default 4px on purpose
- What we are NOT: no dense tables, no admin-gray (#F5F5F5 + borders
  everywhere). If it looks like a hospital scheduling tool, it failed.
```

Every token carries a stated reason tied to anchor or audience. That is the
difference between a derived system and a random one, and it gives the
interviewer something to probe ("why 15px?" has an answer).

## Speed notes

- One turn, no research beyond two public sources. Bound the output: three
  files, every emit-checklist line answered, nothing longer than it needs to be.
- It is fine to have Claude write these files entirely. AI-written prompts and
  harness files are not cheating; they are the job.
- Never ideate inside a prototyping tool. The harness gets built here, in text,
  before v0/Lovable/Claude ever sees a prompt.
- If screenshots arrive mid-build, redo only design-system.md. context.md and
  prototyping.md rarely change.
- **Output location**: write the three files to the working directory unless
  the user names a directory. Do not invent extra files (a `run-notes.md` or
  similar) to hold the closing report. It goes where "Closing report" below says.

## Pre-close self-check

Run these before you write the closing report. Each is a two-second grep or
glance, and each catches a failure that has actually shipped from this skill.

- [ ] Grep the three files for the em dash character. Zero hits inside anything
      user-facing: cast sample lines, copy examples, the build prompt. Prose
      explaining a token may use ordinary punctuation.
- [ ] Grep for `-` between two numbers in `design-system.md`. Any surviving
      range ("12-16px", "16-24px") is a bug; pick one value.
- [ ] Every brand-vs-in-product hex conflict resolved to one canonical value,
      alternative in parentheses. No "or" between two hexes.
- [ ] Every contrast claim carries a hex pair and a computed ratio, or says
      "contrast not verified."
- [ ] The emit-checklist above is fully satisfied, including line-height on
      every type token and four separate state values.
- [ ] The thinness report appears exactly once, in the closing line. Grep the
      written files for "thinnest" and for "Thinnest part"; both must return
      nothing.
- [ ] The full build prompt above is written out, not just referenced.

## Closing report

There is exactly one report, and it is the final line of your response, with no
separate file for it, no earlier draft of it elsewhere. Fixed format:

> Built `<files>` for `<product>` (`<mode>`). Thinnest: `<file>`, because
> `<why>`. `<one input>` would fix it.

Fill `<one input>` by mode:
- **Brownfield**: a specific screenshot ("a screenshot of the My Network Catch
  up tab"). Since there is no live user in most runs, this doubles as the
  screenshot request. Do not also ask separately or wait for a reply.
- **Greenfield**: not a screenshot (there's no product to screenshot). Give
  buyer/segment framing to confirm, or a named competitor screenshot to
  benchmark against.

No other file, and no restating of the report elsewhere, is part of this contract.

## Terminate on the bridge

The run does not end on the thinness report. It ends on a build prompt, written
out in full, for the first concept. Naming the concept is not enough; a name
does not render. Write the prompt the way it would be pasted into a tool, with
all four elements present (task steps, context, desired output, what you do not
want), then stop. This is the last thing in the response, immediately after the
closing report.

> Next: `concept-catchup.html`. Paste this:
>
> "Build a single self-contained HTML file, inline style and inline script, no
> external requests. Rebuild LinkedIn's My Network Catch up tab as a ranked
> list of five people worth reaching out to this week. Use the tokens in
> design-system.md and the urgent-seeker persona and named cast in context.md,
> so every row is a real name with a real reason and a real date. Each row: one
> primary action, one dismiss. Output one screen at roughly 200 lines. Do not
> build a settings page, onboarding, an empty state, avatars loaded from a URL,
> or any copy with a bracket placeholder in it."

A harness run that ends without that block is incomplete, no matter how good
the three files are. Pixels are the deliverable; the harness is the setup.

## Ship the interview-day folder

When the run is for a real interview (the user says "interview is tomorrow",
"make me interview ready", "clean my setup", or the calibration date is within
48 hours), the harness build ends with one more artifact: a sanitary copy of
this whole setup that the candidate can open in front of the interviewer.

Interviewers ask to see under the hood. Jiaona Zhang says it outright: she has
candidates screen share exactly to check who is actually AI-native. So the
folder they see should read like a builder's toolkit ("look at these pre-baked
skills I have"), with none of the practice machinery in it.

Create a sibling folder named for the work (`pm-prototyping/`, never
"interview-harness", never anything with "cheat" or "prep" in the name) and
copy in only what earns its place on a shared screen:

**Keep** (the show-off kit):
- `CLAUDE.md` + `AGENTS.md`, edited so no line references a stripped file
- `skills/design-system/`, this skill, `skills/prd-solidifier/`,
  `skills/prompt-hardener/`, `skills/diverge/`, `skills/backend-builder/`,
  `skills/taste/`
- `references/multi-model-routing.md`, `assets/prd-template.md`
- The target product's built harness: `design-system.md`, `context.md`,
  `prototyping.md`

**Strip** (the gym you trained in):
- `skills/mock-interview/`, `skills/interview-grader/`
- `references/scorecard.md`, `references/scripts.md`,
  `references/question-bank.md`, `references/question-bank-research-log.md`,
  `references/gotchas.md`
- `practice-log.md`, `harness-runs/`, any graded transcripts, this section's
  own paragraphs if they survive into the copy

Then run the read-over-my-shoulder pass on every remaining file: each one
should be about building (tokens, taste, shipping rules), show judgment, and
carry the candidate's own customizations. A personalized harness reads as
experience. A stock download reads as a download.

Close with the preflight checklist, out loud:

- [ ] Harness built for the target company's product from real screenshots or its CSS
- [ ] Tools logged in, free-tier limits checked (a login wall at minute 12 is a self-inflicted wound)
- [ ] One test render fired this morning: prompt in, `concept-test.html` out, opened in a browser
- [ ] Terminal font up, notifications off, practice folder closed. Closed, not minimized.

None of this hides anything. A prepared build environment is the job, and "I
built my setup in advance" said proudly is a competence signal. This step just
makes sure the setup on screen is the setup that does the work.
