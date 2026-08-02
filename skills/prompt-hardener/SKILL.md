---
name: prompt-hardener
description: Hardens the candidate's draft build prompt into all four elements, pulling context from the harness, and arms them with a two-sentence defense. Use when the user says "harden this prompt", "is this prompt good", or reaches the Prompt step of a run.
---

# Prompt Hardener

Input: the candidate's draft build prompt, or just their chosen concept plus the
harness files. Output: the final build prompt with all four elements present and
labeled, plus the defense of it.

Here's the thing: a prompt missing "what you do not want" is a different
prompt, one that grows a fake settings page nobody asked for. This is the step
candidates rush because it feels like overhead. It's actually where the real
work is. Don't skip it.

Never ask more than one question before producing. Produce, then flag what you
assumed.

## The four elements, hardened

1. **Task steps**: in the candidate's build order, numbered. The model builds
   in your order.
2. **Context**: point at `design-system.md` tokens and the PRD definitions from
   `skills/prd-solidifier/SKILL.md` output; inline only what the render tool
   cannot read from files. Never restate the product from memory.
3. **Desired output**: one self-contained `concept-<name>.html` per
   `prototyping.md`, so it renders in one click.
4. **What we do not want**: minimum four bans (lorem ipsum, placeholder names,
   em dashes, invented nav), plus at least one ban specific to this concept.
   This is the element candidates drop, and the render always shows it.

## Worked example

Concept: a "curator" home feed for a music app, PRD says goal is longer weekly
listening time for playlist-making users. Here's what a hardened prompt looks
like end to end:

> **Task steps:** 1) build the top nav and curator profile header first, static.
> 2) build the feed list of playlist cards with play/save actions. 3) wire
> click-to-expand on one card only, showing track list. 4) add the "New from
> people you follow" rail last.
>
> **Context:** use tokens from `design-system.md` (spacing, type scale, the
> brand green `#1ED760`-equivalent token, not a hardcoded hex). Curator segment
> and the "playlists made per week" metric are defined in the PRD; do not
> invent a different north star.
>
> **Desired output:** one file, `concept-curator-feed.html`, self-contained,
> inline style and script, renders in one click, roughly 200 lines.
>
> **What we do not want:** no lorem ipsum, no "Playlist 1" / "User Name"
> placeholders, no em dashes anywhere in the copy, no invented nav items
> beyond Home/Search/Library, plus one ban specific to this concept: no fake
> "Premium upsell" banner, because that's not the surface being tested here.

That's the whole prompt. Notice the specific ban at the end is earned by this
concept.

## The defense

Hand the candidate two sentences for when the interviewer asks why the prompt is
good, because they will ask. Shape: name the four elements, then name the one
choice specific to this build ("the do-not-want bans invented nav items because
LinkedIn prototypes always grow a fake tab").

Said aloud, for the worked example above: "I gave it task steps in my build
order, pointed it at the design system instead of describing colors from
memory, scoped the output to one file, and banned four specific things
including a fake premium banner, because that's not what we're testing today."
Two sentences. Say it like you mean it, because you wrote it.

AI-written prompts are not cheating; undefendable ones are. What is tested is
whether you could have written it yourself, and articulating the four elements
demonstrates that faster than typing under pressure.

## Handoff

Run the hardened prompt past `skills/taste/SKILL.md` instincts in five seconds:
would this prompt embarrass the candidate if read aloud? Then fire it per
`references/multi-model-routing.md`.

## Output voice

Two different modes, do not mix them up.

- **Practice / review mode:** talk like a coach. Bucket the four elements,
  quote back the candidate's own draft where it's weak ("your do-not-want list
  had one ban, you need four"), give the worked example, close with
  encouragement. This is the voice above.
- **Live mode:** quiet mode. The candidate is screen sharing. Output the
  hardened prompt and the two-sentence defense, nothing else. No labels, no
  "here's what I changed," no coaching visible on screen. Per CLAUDE.md's
  quiet-live-mode rule, the only build artifact that should be on screen is
  the file the interviewer would expect to see.
