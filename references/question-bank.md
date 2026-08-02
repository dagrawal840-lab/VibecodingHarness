# Question bank

Practice questions for mock runs. Brownfield unless marked greenfield. Pull one
at random; do not let the user pick a product they know cold every time. Comfort
is the enemy here. The candidate who practiced only Spotify freezes on Salesforce.

Every question below carries a **Trap** line: the hidden failure mode the question
is built to trigger. Read the trap only after you attempt the question.
In mock-interview mode (skills/mock-interview/), the grader checks whether the
candidate fell for it and scores it under the relevant area in
references/scorecard.md.

Every question also carries a provenance tag on its first line:
**[REAL — Company, source, year]** means the question (or a close paraphrase)
was actually reported by a candidate or published by a named source.
**[SYNTHETIC]** means it was authored for this bank. **[SYNTHETIC — modeled on
real X report]** means it is a variant built from a real report. Real questions
from anonymous forums are paraphrased and unverified; see Provenance notes at
the end and references/question-bank-research-log.md for sources.

How to run one: full UPS-PPPB sequence, ~28-minute budget, four prompt elements
in every build prompt (task steps, context, desired output, what you do not
want). Open the actual product in the first two minutes. Opening the product
outscores any framework. And never ideate inside the prototyping tool; ideate on
paper or in chat, then prompt.

## Consumer

1. **[SYNTHETIC]** LinkedIn: improve how people maintain professional relationships (not build new ones).
   - Trap: the parenthetical. Most candidates drift back to "connect with new people"
     by minute 10 because every LinkedIn surface pushes growth. Maintaining means
     dormant ties: the ex-coworker you have not messaged in 14 months. A strong run
     prototypes a "reconnect queue" using visible signals (job change, work
     anniversary) instead of another feed.

2. **[SYNTHETIC]** Spotify: help listeners rediscover music they loved but stopped playing.
   - Trap: recommendation-engine cosplay. Candidates describe an algorithm instead
     of a surface. You cannot prototype a model in 28 minutes; you can prototype
     "Your 2021 obsession: Phoebe Bridgers, 340 plays, 0 in the last year" as a
     card. Prototype the moment, assume the data.

3. **[SYNTHETIC]** YouTube: improve the experience of learning a skill across many videos.
   - Trap: rebuilding a course platform. YouTube is not Coursera and the interviewer
     knows it. The win is stitching existing videos into progress (a saved path,
     a "you left off at chord transitions" resume state) instead of inventing a curriculum.

4. **[SYNTHETIC]** Airbnb: reduce trip-planning drop-off between saving a listing and booking.
   - Trap: ignoring that booking is multiplayer. Solo-user solutions (reminders,
     price alerts) miss that most drop-off is "waiting on my group to agree."
     If the prototype has no second person in it, the diagnosis was wrong.

5. **[SYNTHETIC]** Instagram: make DMs useful for creators drowning in requests.
   - Trap: building for the fan instead of the creator. The user is the person with 4,000
     unread requests. Prioritize triage over chat. Bonus trap: AI auto-replies in the creator's
     voice raise an authenticity guardrail; a strong candidate names it unprompted.

6. **[SYNTHETIC]** Netflix: solve "30 minutes of browsing, nothing watched."
   - Trap: "add a Surprise Me button" in minute 3. It already exists (Play Something,
     shipped 2021). Punishes candidates who never opened the product. The real
     problem is decision cost in groups and mood mismatch; randomness was never the gap.

7. **[REAL — reported prompt type, Product Growth newsletter, 2026]** Design Google Maps for the blind, then prototype the core flow.
   - Trap: prototyping a map. A visual map is the one artifact your user cannot use.
     The honest prototype is audio-first: a turn-by-turn narration script, haptic
     cue settings, a "describe my surroundings" button. Candidates who ship a
     grayed-out map with bigger labels reveal they never switched modalities.

8. **[REAL — reported prompt type, Product Growth newsletter, 2026]** How would you prototype a Facebook Dating app?
   - Trap: cloning Tinder inside Facebook chrome. The only reason Facebook Dating
     exists is the social-graph asymmetry (friends-of-friends, shared events,
     mutual groups) plus the privacy landmine (your aunt must never see your
     profile). A swipe deck without a visibility-control screen misses the
     entire reason the question is hard.

9. **[SYNTHETIC]** TikTok: help users act on the recipes, products, and places they save but never revisit.
   - Trap: building a better bookmark folder. Saves die because they are stripped
     of context at retrieval time. The prototype that wins resurfaces the save at
     the actionable moment: the saved restaurant when you are in that city, the
     recipe on Sunday grocery day. A well-timed trigger beats better taxonomy.

10. **[SYNTHETIC]** WhatsApp: make group planning (trips, dinners, gifts) less chaotic without making WhatsApp feel like a productivity app.
    - Trap: bolting a project tracker onto a chat. WhatsApp's whole value is zero
      ceremony; a Kanban board inside a family group chat is dead on arrival. The
      constraint in the question ("without making it feel like...") is the spec:
      structure that emerges from messages (auto-detected polls, dates, tallies)
      instead of structure users must create.

11. **[SYNTHETIC]** Strava: keep runners engaged through injury, when they cannot log the activity that defines the app.
    - Trap: cheering harder at someone who cannot run. Streak nudges and kudos on
      old runs rub salt in. The strong run reframes identity: recovery as a
      loggable activity type, a return-to-running plan, a "watching my crew" mode.
      Name the guardrail: no guilt notifications to injured users.

12. **[SYNTHETIC]** Google Photos: help users do something with 40,000 photos besides storing them.
    - Trap: proposing "AI auto-albums," which already exist (Memories). The unmet
      job is outbound: turning the archive into a shared artifact (the grandparents'
      digest, the year-end book, the friend-group drop). Prototype the output
      object instead of another sorting layer.

13. **[SYNTHETIC]** Reddit: improve the first week for a lurker who just made an account.
    - Trap: pushing the lurker to post. 90%+ of Reddit value is consumption, and
      week-one posts get downvoted into churn. Retention comes from three good
      subreddit joins; one bad post matters far less. A prototype that ends in a submit button
      optimized the wrong verb.

14. **[SYNTHETIC]** Uber: improve the experience of waiting for a ride that is 11 minutes away.
    - Trap: trying to shrink the 11 minutes. Dispatch is not yours to fix in this
      round. The prototype-able surface is the wait itself: confidence the car is
      really coming, what to do when the pin is wrong, the walk-to-corner nudge
      that saves two minutes. Candidates who redesign matching burn the clock on
      a backend they cannot show.

15. **[SYNTHETIC]** Amazon: help shoppers confidently buy things they cannot try, in categories with 40% return rates (apparel, furniture).
    - Trap: defaulting to AR try-on. It demos well and every candidate says it.
      The cheaper, prototype-able wedge is structured fit truth from returns data:
      "runs small, 62% of buyers your height sized up." Returns are Amazon's data
      moat; use the moat instead of the gimmick.

16. **[SYNTHETIC]** Pinterest: close the gap between saving an idea (a room, an outfit) and actually executing it.
    - Trap: treating the board as the product. The board is where intent goes to
      die. Prototype the execution layer: board-to-shopping-list, board-to-plan,
      "you saved 30 kitchens, here are the 3 decisions they imply." If the final
      screen is still a grid of pins, nothing changed.

17. **[SYNTHETIC]** Snapchat: design something that makes 25-plus users open the app again without alienating the core teen base.
    - Trap: aging the product up. Anything that makes Snap feel like Facebook
      kills it for teens, and the interviewer knows the graveyard of "Snap for
      adults" ideas. The defensible wedge is a use case adults already half-do
      (close-friends photo streams with family) that teens never see. Name the
      cannibalization guardrail out loud.

18. **[SYNTHETIC]** Duolingo: win back users who quit after losing a long streak.
    - Trap: fixing the streak mechanic. The streak did its job; the failure is the
      re-entry moment, where the app greets a lapsed user with the evidence of
      their failure. Prototype the comeback screen ("your 214-day streak is frozen,
      not dead"), and name the guardrail: guilt notifications churn people harder.

## B2B / prosumer

19. **[SYNTHETIC]** Notion: help teams find the one true version of a doc.
    - Trap: answering with search. "Better search" finds five versions faster; it
      does not tell you which one is canonical. Canonical status is a social claim
      (owner, freshness, endorsement), so the prototype needs a trust signal on the
      doc, so the prototype needs a trust signal rather than a better query box.

20. **[SYNTHETIC]** Figma: improve handoff friction between design and engineering.
    - Trap: designing only for the designer. The person in pain is the engineer
      reading the file. If the prototype never shows the engineer's view, half the
      problem was skipped. Also: Dev Mode exists; know what it already does.

21. **[SYNTHETIC]** Slack: reduce the cost of returning from a week of PTO.
    - Trap: "AI summary of everything you missed." Too obvious and too flat; every
      candidate says it. Differentiate on triage: what needs a reply from you, what
      resolved itself, what can die. A summary you still have to read is not a
      cost reduction.

22. **[SYNTHETIC]** Zoom: make the first 90 seconds of external meetings less awkward.
    - Trap: scope creep into "reimagine meetings." Ninety seconds is the brief.
      The narrow scope is a gift for prototyping: one pre-join screen, one warm-up
      state, done. Candidates who widen the scope run out of clock.

23. **[SYNTHETIC]** Shopify: help a first-time merchant get from signup to first sale.
    - Trap: optimizing the setup checklist. Setup completion is not the metric;
      first sale is, and first sale happens off-platform (the merchant's Instagram,
      their group chats). The brave prototype pushes the merchant out the door
      to share instead of deeper into settings.

24. **[SYNTHETIC]** Salesforce: get reps to actually log activity without hating it.
    - Trap: "gamify it." Reps see through points instantly. The honest insight is
      that logging is pure tax with zero rep-side value; the fix is capture-for-free
      (auto-draft from email and calls, rep confirms in one tap); motivation was never the problem.

25. **[REAL — PMCurve prep bank (unattributed), 2026]** Build a simple CRM where a user can add, edit, and delete customers — then make it something a real salesperson would open twice.
    - Trap: stopping at CRUD. The literal ask is a 10-minute build, and weak
      candidates spend 25 polishing it. The second clause is the interview: a rep
      opens a CRM for "who do I call today," so the differentiator is a
      next-action queue seeded with realistic deal data, not a prettier table.

26. **[REAL — PMCurve prep bank (unattributed), 2026]** Build a customer support chatbot that answers FAQs and escalates to a human.
    - Trap: demoing only the happy path. The whole question lives in the
      escalation seam: when does the bot admit defeat, what context does the human
      inherit, does the user re-explain from zero? A run that never shows the
      failure-to-handoff state skipped the hard 20% the question names.

27. **[REAL — PMCurve prep bank (unattributed), 2026]** Create a landing page for a meditation app (think Headspace) that converts visitors to sign up.
    - Trap: shipping a generic hero-features-testimonials page. The word
      "converts" is the brief. Strong runs pick one anxiety-specific promise, one
      CTA, and state the conversion metric and the A/B they would run. A page
      with four CTAs and stock-copy calm gradients is the AI default; leaving it
      unedited is the fail.

28. **[SYNTHETIC]** Calendly: help a recruiter scheduling 40 candidate interviews a week across 12 interviewers.
    - Trap: solving the single-link case Calendly already owns. The recruiter's
      pain is orchestration: panel availability intersection, reschedule cascades,
      the candidate who goes dark. Prototype the recruiter's ops dashboard, not
      another booking page.

29. **[SYNTHETIC]** Atlassian/Jira: make sprint status legible to stakeholders without making engineers update tickets more.
    - Trap: violating the constraint in the second clause. Any solution that adds
      engineer data entry is an automatic miss. Status must be inferred from what
      already moves (commits, PRs, ticket transitions) and rendered for the VP
      who will never open Jira. Two audiences, one of whom must do zero new work.

30. **[SYNTHETIC]** HubSpot: help a 5-person startup send marketing email that does not feel like marketing email.
    - Trap: building a template gallery. Templates are why the email feels like
      marketing. The wedge is founder-voice drafting from real product activity
      ("you shipped X, tell the 200 users who asked for it") with a send-size
      guardrail. Small-list authenticity beats enterprise campaign machinery.

31. **[SYNTHETIC]** Dropbox: give the file-hoarder professional (10 years, 80,000 files) a reason to stay when storage is a commodity.
    - Trap: competing on organization. Nobody re-organizes 80,000 files, and
      auto-tagging demos are stale. The retention wedge is the archive as an
      asset: "the proposal deck you wrote in 2019 is 80% of the one you need
      today." Retrieval-at-moment-of-need, prototyped as a sidebar in the
      creation flow rather than a cleaner folder tree.

32. **[SYNTHETIC]** Canva: help a social media manager produce 30 on-brand posts a week without the brand kit becoming a straitjacket.
    - Trap: picking a side of the tension instead of prototyping it. Full
      automation ships off-brand slop; full lockdown is why designers hate brand
      portals. The artifact that wins shows the guardrail spectrum: locked logo
      and palette, flexible layout, an "off-brand" warning state. Show the
      boundary as well as the generator.

## AI-native

33. **[SYNTHETIC]** ChatGPT/Claude: help users build durable workflows instead of one-off chats.
    - Trap: prototyping a chat UI. If the concept HTML is a message thread, the
      question was not answered. Durable means reusable and scheduled: saved
      prompts, templates, recurring runs. The artifact should look like a library
      or a dashboard rather than a conversation.

34. **[SYNTHETIC]** Perplexity: design the research experience for a student writing a thesis.
    - Trap: treating research as a single session. A thesis is three months of
      accumulating sources, claims, and contradictions. Prototype persistence
      (a project workspace with a claims-and-evidence board), and name the
      guardrail: citations the student can verify, or the tool is a liability.

35. **[SYNTHETIC]** Cursor: help a PM (not an engineer) get value in their first session.
    - Trap: teaching the PM to code. The parenthetical again. First-session value
      for a PM is "I turned my PRD idea into a clickable page," so the prototype
      is an onboarding path that hides the terminal rather than a tutorial that opens it.

36. **[REAL — Meta, IGotAnOffer candidate report, 2026]** Design and prototype an app that helps people find and commit to local volunteering opportunities.
    - Trap: the second half of the sentence. Finding opportunities is a search
      problem every candidate solves; commitment is the graveyard (signup-to-show-up
      rates are brutal). The reported Meta follow-ups went straight at the build:
      token usage, latency, why not image generation. Expect your prompting to be
      cross-examined, and put the commitment mechanic (calendar hold, crew of
      friends, org confirmation) in the prototype rather than the pitch.

37. **[REAL — Meta, Prepfully, 2026]** Design a product for borrowing and lending physical household goods on Facebook.
    - Trap: skipping the trust ledger. A listings feed is Marketplace with a
      "borrow" label. The whole product is what happens when the drill comes back
      broken: deposits, condition photos, the mutual-friends trust signal only
      Facebook has. If the prototype has no return flow, it is a rental ad board.

38. **[REAL — Meta, Prepfully, 2026]** Design a system that builds a digital job-application profile from a photo of a resume.
    - Trap: demoing perfect extraction. OCR-to-profile is a solved demo; the
      product is the error surface. Prototype the confirm-and-correct screen with
      confidence states ("we guessed 2019-2021, check this") and name the
      guardrail: a hallucinated job title on an application is a fireable harm,
      so nothing auto-submits unreviewed.

39. **[REAL — Meta, Prepfully, 2026]** Design a smart trash can for a modern kitchen that helps users sort recycling and compost automatically.
    - Trap: burning the clock on hardware. You cannot prototype a torque hinge in
      a vibe coding tool; you can prototype the companion surface: the
      misclassification correction flow, the "your city does not accept #5
      plastics" localization, the weekly diversion report. Candidates who
      storyboard industrial design ship nothing clickable.

40. **[SYNTHETIC — modeled on real Meta report]** Meta AI: design the assistant experience inside WhatsApp for a user who never chose to have an AI in their chats.
    - Trap: designing for the enthusiast. The named user did not opt in, and the
      failure mode is intrusion (the blue circle backlash was real). Prototype
      restraint: invocation-only presence, a visible "this is AI, your chats are
      unread by it" boundary, one undeniably useful entry point (group poll
      summarizer). Consent before capability.

41. **[SYNTHETIC]** NotebookLM: design the experience for a lawyer who must trust every citation across 200 discovery documents.
    - Trap: selling the magic instead of the audit trail. For this user one
      fabricated citation ends the relationship. The prototype is
      verification-first: every claim click-throughs to the highlighted source
      passage, unverifiable claims visibly quarantined. If your artifact shows
      answers without provenance affordances, you built it for a student, not
      a lawyer.

42. **[SYNTHETIC]** GitHub Copilot: design the experience for the senior engineer who reviews AI-written PRs from juniors all day.
    - Trap: building for the author again. Generation is saturated; review is the
      bottleneck. The reviewer needs provenance density ("this file is 90%
      accepted-as-suggested"), risk-ranked diffs, and a "what did the human
      actually decide" view. Prototype the reviewer's queue rather than a better
      autocomplete.

43. **[SYNTHETIC]** ElevenLabs: let a podcaster license an AI clone of their voice without losing control of it.
    - Trap: prototyping the cloning wizard and skipping the control plane. The
      podcaster's real question is "what is my voice saying right now, and can I
      kill it?" Build the rights dashboard: active licenses, usage log, per-use
      approval tiers, a revoke button that visibly works. Consent infrastructure
      is the product; the clone is a commodity.

44. **[SYNTHETIC]** Character.ai: design guardrails for emotionally dependent heavy users without gutting the product they love.
    - Trap: picking the corporate answer (hard limits) or the growth answer
      (nothing). Both lose. The scored behavior is holding the tension: prototype
      graduated friction (session awareness, off-ramps to humans, dependency
      signals routed to a safety flow) and say plainly that engagement time is
      the wrong north star here. Name whose metric you are willing to hurt.

45. **[SYNTHETIC]** v0/Lovable: design the recovery experience for the moment a non-technical user's generated app breaks and they cannot read the error.
    - Trap: answering "make the AI fix it silently." Silent auto-repair teaches
      the user nothing and fails eventually; a raw stack trace churns them
      instantly. Prototype the translation layer: plain-language diagnosis, one
      "fix it" primary action, an honest "this needs a developer" state.
      Meta-point the interviewer is watching: you are in this exact tool right
      now; behave like the user you are designing for.

46. **[SYNTHETIC]** OpenAI/Anthropic: design a "memory" control surface so users trust what the assistant remembers about them.
    - Trap: burying control in settings. Memory dies or thrives at the moment of
      surprise ("how did it know that?"). Prototype in-flow affordances: the
      inline "remembered from March 12" chip, one-tap forget, a visible line
      between remembered and inferred. A settings toggle list is where trust
      problems go to be ignored.

## Marketplace

47. **[SYNTHETIC]** Etsy: protect "handmade" buyers from AI-generated product listings without accusing sellers publicly.
    - Trap: proposing a ban you cannot enforce. Detection is unreliable and false
      accusations destroy legitimate sellers, which the question's second clause
      warns you about. Prototype disclosure economics instead: a verified-process
      badge worth real search placement, seller-side evidence upload, buyer
      filters. Incentives work better than policing.

48. **[SYNTHETIC]** DoorDash: fix the moment an item is missing from a delivered order, for all three sides.
    - Trap: solving only the refund. The customer wants dinner; $4 back does not fix that. The
      dasher gets blamed for the restaurant's error; the restaurant never learns.
      A three-sided flow (instant customer resolution, dasher exoneration by
      sealed-bag photo, restaurant error report) is the answer. One-sided
      prototypes score as one-third answers.

49. **[SYNTHETIC]** Upwork: help a first-time client write a job post that attracts the right freelancers instead of 90 spam bids.
    - Trap: improving the post template. The post is not the problem; the flood
      is. Prototype the intake interview that turns a vague need into scoped
      milestones plus a shortlist-of-five experience with bid quality signals.
      If your artifact still ends in an open bid pile, the client's morning is
      unchanged.

50. **[SYNTHETIC]** StubHub: make buyers trust that the ticket will actually work at the gate.
    - Trap: waving at "verification" without prototyping the anxiety timeline.
      Trust fails at three moments: purchase (is this real?), day-before
      (where is my transfer?), gate (it scanned red, now what?). The artifact
      that wins is the reassurance timeline with a live gate-failure protocol,
      not a trust badge on the listing page.

51. **[SYNTHETIC]** Instacart: handle out-of-stock substitutions so customers stop feeling gambled with.
    - Trap: making the customer approve every swap live. They are in a meeting;
      that is why they ordered groceries. The fix is preference capture before
      the shop (brand-loyal vs size-flexible per item class) plus a shopper view
      that shows the rule being applied. Prototype both sides or the shopper
      just guesses with extra steps.

52. **[SYNTHETIC]** Zillow: help a first-time buyer who tours homes every weekend but never makes an offer.
    - Trap: reading it as a discovery problem and adding filters. Discovery is
      saturated; the paralysis is decision fear (overpaying, missing better,
      unknown process). Prototype the decision scaffold: side-by-side tour
      notes, a "what would an offer look like" simulator, next-step
      demystification. The user has seen enough homes.

53. **[SYNTHETIC]** Turo: design the damage-dispute experience so both host and guest feel the process is fair.
    - Trap: designing for one side's outcome instead of both sides' evidence.
      Disputes are decided by check-in/check-out photo quality, so the
      prototype is the guided capture flow (same angles, timestamped, both
      parties) plus a claims timeline with visible status. Fairness is
      symmetric evidence, and friendlier support copy will not substitute.

54. **[SYNTHETIC]** Fiverr: help sellers survive the shift where AI does 80% of what their cheapest gigs offered.
    - Trap: pretending the tide is stoppable. Banning AI or hiding the problem
      insults the interviewer. The honest move is repositioning inventory:
      migrate sellers up the stack (AI-assisted delivery with human taste,
      revision guarantees, outcome pricing) and prototype the seller's
      "modernize my gig" flow. Say the uncomfortable premise out loud first.

55. **[SYNTHETIC]** Airbnb: design the experience for the 3 a.m. arrival where the lockbox code does not work.
    - Trap: routing to support chat. At 3 a.m. with luggage, a queue is abandonment.
      The bar is resolution-without-humans: verified backup entry paths staged
      before the trip, an escalation ladder with hard time guarantees, and a
      "get me a room now" fallback Airbnb pays for. Prototype the worst night,
      and the trust story tells itself.

56. **[SYNTHETIC]** Booking.com marketplace side: help small independent hotels compete with chains on a platform optimized for conversion at their expense.
    - Trap: forgetting who the user is. This is a supply-side question; candidates
      slide back to traveler UX within minutes. The independent hotelier's levers
      are story, locality, and direct relationships, all flattened by the
      standard listing template. Prototype the property's control surface, and
      name the platform conflict: Booking profits from commoditized supply.

## Fintech

57. **[SYNTHETIC]** Venmo: make splitting recurring costs (rent, utilities, subscriptions) not require a spreadsheet-keeping roommate.
    - Trap: prototyping a one-time split, which already exists. Recurring is the
      word: standing splits, auto-request on due date, the delinquency state when
      one roommate ghosts. The awkwardness of the nag is the design problem;
      the app should play the bad guy instead of the roommate.

58. **[SYNTHETIC]** Stripe: help a founder understand why their revenue dipped last Tuesday.
    - Trap: prototyping a dashboard. A wall of charts restates the question. The
      question is "why," so the artifact is a narrative diagnosis ("failed renewals
      from EU cards spiked after the 3DS change") with drill-down instead of more graphs.
      Realistic placeholder numbers matter double here; "$1,234" reads as lorem ipsum.

59. **[SYNTHETIC]** Robinhood: design the experience for a user who just lost 40% on options they did not understand.
    - Trap: reading it as an education problem and shipping a tutorial. Nobody
      reads a tutorial after losing rent money. The regulated-space answer is
      friction-by-design before the next trade (comprehension gates, cooling
      windows, plain-loss disclosure) and a non-patronizing aftermath screen.
      Name the conflict: Robinhood monetizes the order flow you are throttling.

60. **[SYNTHETIC]** Chime: help a paycheck-to-paycheck user survive the week before payday without payday-loan economics.
    - Trap: prototyping a budgeting dashboard. A user \$40 short on Tuesday does
      not need a pie chart of past spending; they need forward cashflow ("rent
      clears Thursday, you are \$12 negative Friday") and a bridge that is not a
      debt trap. Guardrail to name: shame-free tone, no red everywhere; this
      user already knows they are broke.

61. **[SYNTHETIC]** Coinbase/Kraken: design the panic moment. Market down 30%, user opens the app at 2 a.m.
    - Trap: optimizing the trade path. The easy build is a faster sell button,
      which maximizes both user regret and exchange fees. The honest artifact
      adds one breath of friction: portfolio-in-context ("you are down 8%, not
      30%"), a historical drawdown frame, then unblocked action. Regulated
      space: no "hold on, it'll recover" advice; that is a compliance line,
      say so.

62. **[SYNTHETIC — modeled on Kraken take-home reports]** Kraken-style 48-hour take-home: prototype a feature that makes a first-time crypto buyer confident enough to complete their first $100 purchase.
    - Trap: treating a take-home like a live round. With 48 hours, a
      28-minute-quality artifact reads as low effort; the bar moves to seeded
      realistic data, three states (novice, hesitant, completed), and a written
      why-this memo. The scope trap still applies: one confident purchase flow,
      not a whole exchange.

63. **[SYNTHETIC]** Intuit/TurboTax: help a gig worker with 1099s from four apps not dread tax season all year.
    - Trap: building a better April. The dread is a 12-month problem; the fix is
      quarterly ("you should set aside \$340 from this month's driving").
      Prototype the year-round companion state, and name the compliance
      boundary: estimates are estimates, and the product must say so on every
      number.

64. **[SYNTHETIC — modeled on Airwallex loop reports]** Airwallex: help a small e-commerce founder who sells in six currencies understand what they actually earned last month.
    - Trap: showing exchange rates instead of answers. The founder's question is
      "did I make money," which FX noise obscures. Prototype the normalized P&L
      ("you earned \$8.2k; FX cost you \$310; here is the one currency worth
      hedging") with drill-down. A currency dashboard restates the confusion
      in more colors.

65. **[SYNTHETIC]** Klarna: design the moment of declining a BNPL purchase so it protects the user without humiliating them at checkout.
    - Trap: dodging the decline screen. Candidates prototype approval flows
      because declines are unpleasant, but the decline IS the assignment.
      Strong runs make it private, reasoned ("this would be your fifth active
      plan"), and forward-looking (path back to eligibility). Name the tension:
      the merchant paying Klarna wants that sale to happen.

66. **[SYNTHETIC]** A bank asks you to design its first AI money coach for people under 30. (greenfield)
    - Trap: the conflict of interest. The bank profits from overdraft fees and
      credit interest; the coach's advice cuts that revenue. Candidates who never
      name the trust problem lose the exec-alignment point. Also regulated space:
      "AI gives financial advice" needs a compliance boundary stated out loud.

## Health

67. **[SYNTHETIC]** MyChart/Epic patient portal: help a patient understand lab results that arrive before their doctor's explanation.
    - Trap: having the AI interpret the results. "Your creatinine suggests..." is
      practicing medicine; the interviewer is waiting for you to notice. The safe,
      useful surface is context without diagnosis: what this test measures,
      what "flagged" means statistically, questions to bring to the visit, and
      an anxiety-aware "your doctor reviews this by Thursday" state.

68. **[SYNTHETIC]** Headspace/Calm: retain the user who bought a subscription in a January panic and stopped opening the app by March.
    - Trap: re-engagement notifications, which for a meditation app read as one
      more source of stress. The lapsed user's blocker is the identity gap ("I am
      not a meditator"), so the comeback surface is minimum-viable practice (one
      breath, 60 seconds, no streak) and a no-guilt guardrail named out loud.
      Do not prototype a content library; they already ignored one.

69. **[SYNTHETIC]** Oura/Whoop: design the morning readiness screen for a user whose data is bad news three days in a row.
    - Trap: letting the score punish. Three red mornings teach users to stop
      wearing the ring. The redesign decouples data from judgment: "here is
      what changed, here is one adjustable input" beats a 54 in red type. Name
      the health-anxiety guardrail and the line the product must not cross:
      sleep data is not a sleep-disorder diagnosis.

70. **[SYNTHETIC]** Teladoc: design the 15 minutes before a first-ever video doctor visit.
    - Trap: treating it as a waiting room to fill with content. The pre-visit
      window is for prep rather than entertainment: symptom summary the doctor actually
      receives, camera/mic check with graceful fallback to phone, what-to-expect
      script for the telehealth-skeptical. If the doctor arrives and asks "so
      what brings you in" cold, your 15 minutes did nothing.

71. **[SYNTHETIC]** CVS/Walgreens app: help a caregiver manage prescriptions for themselves plus two aging parents.
    - Trap: designing for one patient profile. The caregiver juggles three
      people's refills, interactions, and pickup runs under HIPAA-shaped consent
      walls. Prototype the household view with per-person consent states and a
      unified pickup batch. Ignoring the authorization problem means the
      prototype is illegal, and the interviewer knows it.

72. **[SYNTHETIC]** Flo/Clue: rebuild trust in a period tracker for users worried about who can see their data.
    - Trap: answering with a settings page and a privacy policy link. Post-Dobbs,
      the fear is subpoenas rather than ad targeting. Credible moves are architectural,
      and the product must show them, not merely claim them: local-only mode with visible tradeoffs,
      delete-everything that proves deletion, plain-language threat model.
      A padlock icon is not an answer.

73. **[SYNTHETIC]** Noom/weight-loss app: design for the user on GLP-1 medication whose problem is no longer willpower.
    - Trap: shipping the old psychology playbook to a user whose appetite is
      chemically handled. Their actual needs shifted: protein adequacy, muscle
      retention, side-effect days, and what happens off-med. Candidates who
      prototype another habit-streak coach missed that the market moved under
      the product; naming that shift is the point of the question.

74. **[SYNTHETIC]** One Medical: fix "I have a weird symptom, is this urgent?" without a triage bot that always says "see a doctor."
    - Trap: the liability-shaped bot. A triage flow that ends every branch at
      "seek care" is legally safe and useless, and the question pre-names it.
      The differentiator is calibrated routing (self-care with watch-fors,
      same-week visit, urgent now) with a human fallback and visible reasoning.
      Say the malpractice guardrail out loud, then design inside it.

## Enterprise / infra

75. **[SYNTHETIC]** Datadog: design the 3 a.m. on-call experience for an engineer woken by a page.
    - Trap: prototyping the dashboard they use at their desk. At 3 a.m. on a
      phone, the user needs three things: is it real, is it mine, what changed.
      One screen, huge type, deploy-diff and blast radius, mute-with-reason.
      Candidates who show a wall of graphs designed for two monitors failed
      the context.

76. **[SYNTHETIC]** AWS: help a startup CTO understand a surprise \$40k bill without a billing PhD.
    - Trap: rebuilding Cost Explorer, which restates the problem instead of solving it.
      The artifact is a diagnosis narrative ("NAT gateway traffic 8x'd after the
      Feb 12 deploy; here are the three lines that did it") plus a one-click
      guardrail (budget alarm at the anomaly source). "Why," then "never again,"
      in one flow.

77. **[SYNTHETIC]** Okta: design the access-request experience so employees stop waiting three days and admins stop rubber-stamping.
    - Trap: optimizing one side. Faster requests without smarter approvals just
      moves the pile; auto-approval without policy is a breach memo. Prototype
      the paired surfaces: requester sees status and precedent ("14 people in
      your role have this"), approver sees risk-ranked queue with one-click
      time-boxed grants. Name the audit-trail guardrail; this is compliance
      territory.

78. **[SYNTHETIC]** Snowflake: help a data team find which of their 4,000 tables is the right one before racking up query costs on the wrong three.
    - Trap: answering with search over table names. Names lie; trust signals
      decide ("core_users_v2 vs users_final_FINAL"). Prototype the canonical
      badge economy: freshness, lineage, who queries it, owner endorsement.
      Same social-claim insight as the Notion question, but with a \$/query
      meter attached.

79. **[SYNTHETIC — modeled on real Adobe loop reports]** Adobe: bring one genuinely useful AI assist into Acrobat for the contracts-all-day paralegal, without hallucination risk touching a legal document.
    - Trap: summarization theater. A summary the paralegal must verify line-by-line
      saves nothing. High-trust assists are extractive rather than generative: clause
      diff against standard terms, defined-term consistency checks, every output
      anchored to a highlighted passage. The constraint clause is the spec;
      generative rewriting of legal text is the trap named in the question.

80. **[SYNTHETIC]** ServiceNow: make filing an IT ticket not feel like punishment, without letting "walk up and ask Dave" chaos return.
    - Trap: laughing at the ticket form and just deleting fields. Structure exists
      because routing needs it. The move is invisible structure: chat-style
      intake that auto-fills category, asset, and urgency from context, with the
      form as fallback. Both clauses are constraints; honoring only one is the
      common miss.

81. **[SYNTHETIC]** Vercel/v0 (platform side): design the moment a hobbyist's side project goes viral and hits usage limits at 2 a.m.
    - Trap: prototyping the upgrade paywall. Hard-stopping a viral moment is how
      platforms lose their best future customers on their best day. The artifact
      is the graceful-degradation ladder: soft limits, a "you're going viral"
      congratulation-plus-decision screen, spend caps the hobbyist sets while
      panicking. Monetize the success, do not decapitate it.

82. **[SYNTHETIC — modeled on real DataRobot loop reports]** DataRobot-style: design the model-monitoring surface that tells a business owner (not a data scientist) their churn model has quietly gone stale.
    - Trap: charts of drift metrics. PSI curves mean nothing to the VP whose
      campaigns run on the model's scores. Translate decay into business terms
      ("this model now misses 3 in 10 churners; it caught 9 in 10 at launch")
      with one decision: retrain, rollback, or pause. The audience in the
      parenthetical is the whole question.

## Media & entertainment

83. **[REAL — Netflix, Product Growth newsletter, 2026]** Netflix homework round: design a Netflix product to support Partner Studios, and bring a prototype.
    - Trap: reading "Partner Studios" as a consumer feature. The user is a studio
      exec deciding where their next show goes; the product is B2B: performance
      transparency (beyond Netflix's notoriously guarded metrics), production
      tooling, pitch-to-greenlight workflow. Candidates who prototype a fan-facing
      studio page answered a different question. Homework format: depth expected,
      seeded data mandatory.

84. **[SYNTHETIC — modeled on real Netflix vibe-coding round reports]** Netflix: design the post-credits moment when a viewer finishes a series they loved.
    - Trap: instant autoplay of "more like this," which is what exists and why
      the question is being asked. Series-end is an emotional beat, and shoving
      a lookalike at it feels like a rebound. Prototype the landing: a moment of
      closure (cast notes, discussion, rate-it), then a bridge chosen for
      mood-adjacency rather than genre-similarity. Consumer-experience focus is the
      reported Netflix pattern; polish matters here.

85. **[SYNTHETIC]** Spotify: make podcast discovery work for someone with 8 subscribed shows and 40 unplayed episodes.
    - Trap: recommending more podcasts to a person drowning in podcasts. The
      backlog is the signal: this user needs triage (which 2 of the 40 are worth
      it) and episode-level discovery (the one great episode of a show they'd
      never subscribe to). Adding to the pile is the failure the question
      describes.

86. **[SYNTHETIC]** YouTube: design the experience for a creator's first 100 subscribers, before the algorithm cares about them.
    - Trap: dashboard-of-zeros. Analytics built for 100k-subscriber channels
      humiliate a channel with 43. The pre-algorithmic phase runs on direct
      distribution (share kits, community seeding) and micro-milestones that
      reframe 43 as progress. Prototype the encouragement machine rather than a
      shrunken Studio.

87. **[SYNTHETIC]** Kindle: help readers get through the books they buy (industry completion rates are dismal).
    - Trap: streaks and reading goals; Kindle has them, and gamifying guilt does
      not finish books. The honest levers are re-entry cost (a "previously on"
      recap after two weeks away) and permission to quit (archive without shame,
      "readers like you finished this alternative"). The metric worth naming:
      second-session return; minutes read misses the point.

88. **[SYNTHETIC — modeled on real NBCUniversal loop reports]** NBCUniversal/Peacock: design the live-sports second-screen experience for the casual fan watching with a die-hard.
    - Trap: building for the die-hard, who is already served (stats overlays,
      RedZone). The casual fan's job is social survival: "why is everyone
      yelling," explained in one glance without pausing live TV. Prototype the
      companion surface with moment-triggered context, and name the guardrail:
      nothing that spoils the die-hard's unspoiled feed.

## India market

89. **[SYNTHETIC — modeled on Google India AI PM vibe-coding reports]** Google Pay India: design the experience that gets a first-time UPI user's parent through their first three payments without a family member on the phone.
    - Trap: assuming your onboarding instincts transfer. This user fears the
      wrong-recipient error more than they value speed: confirmation-heavy
      beats frictionless, voice guidance in their language beats icon literacy,
      and a "practice payment to yourself" beats a tutorial. Scale check the
      interviewer expects: UPI does billions of transactions monthly; edge
      cases are millions of people.

90. **[SYNTHETIC]** Zomato: design for the office lunch order: 12 colleagues, one delivery, split payment, 30-minute window.
    - Trap: prototyping a fancier group cart. The breaking points are social:
      the organizer fronting money, the colleague who orders late, the one veg
      thali in a non-veg batch gone missing. Group-pay links, order deadlines
      that self-enforce, and per-item ownership at handoff are the product.
      Also know Zomato has shipped group ordering; the gap is the office ritual,
      not the cart.

91. **[SYNTHETIC]** Flipkart: reduce cash-on-delivery return-to-origin rates for first-time e-commerce buyers in tier-2/3 cities.
    - Trap: punishing the customer (COD bans, blocklists) in minute five. RTO is
      a trust symptom: the buyer never believed the product would match the
      photo. Work the trust chain: vernacular product videos, doorstep-open
      confidence, delivery-day WhatsApp confirmations with an easy pre-dispatch
      cancel. A blocklist prototype reads as never having met this user.

92. **[SYNTHETIC]** Paytm: help a kirana (corner-store) owner who accepts QR payments all day start using one more financial product.
    - Trap: pitching the app's full financial services menu. The kirana owner
      trusts the soundbox more than the app. The wedge is one product that grows out
      of visible daily behavior: settlement-based micro-credit ("your last 90
      days of QR volume qualifies you"), surfaced through the channel they
      already heed: the soundbox and SMS, rather than a dashboard.

93. **[SYNTHETIC]** Swiggy/Blinkit: design 10-minute grocery for a household where the person ordering is not the person cooking.
    - Trap: single-user assumptions. The daughter in Bangalore orders for the
      mother in the kitchen; the cart is a conversation ("which atta brand?").
      Prototype shared carts with voice notes, brand-preference memory per
      household member, and delivery instructions the cook controls. If one
      phone owns the whole flow, the household was ignored.

94. **[SYNTHETIC]** WhatsApp Business India: help a home-based seller (sarees, tiffin service) run their entire business from chats without losing orders in the scroll.
    - Trap: importing a Shopify mental model. This seller will not maintain a
      catalog website; chat IS the storefront and the CRM. Structure must be
      extracted from the stream: auto-detected order messages pinned to a
      lightweight ledger, payment-received matching, a daily "3 unfulfilled
      orders" digest. The scroll is the database; index it.

95. **[SYNTHETIC]** Ola/Uber India: design for the daily-commute auto-rickshaw rider whose driver cancels twice each morning.
    - Trap: treating cancellations as a rider-UX problem. Drivers cancel because
      short hauls and digital payment delays lose them money; no rider-side
      screen fixes driver economics. The honest prototype touches both sides:
      commute-hour bundles or standing pickups that make the trip worth
      accepting, plus honest rider ETAs that price in cancel probability.
      Name whose incentive is broken.

96. **[SYNTHETIC]** CRED: design a feature that deepens engagement for users who pay bills on the 1st and never open the app again all month.
    - Trap: manufacturing engagement for its own sake. Spin-the-wheel gimmicks
      on a financial app erode the premium-trust brand that IS the moat. The
      credible surface is between-cycle value on the same trust axis: spend
      intelligence, anomaly alerts ("this subscription doubled"), card-benefit
      expiries. If your idea would look at home in a casual game, it is
      off-brand here, and the interviewer is testing whether you notice.

## Europe market

97. **[SYNTHETIC]** Spotify (EU): design the data-transparency experience GDPR forces, and make it a feature users actually like instead of a compliance chore.
    - Trap: shipping a consent wall and calling it done. The question asks for
      the judo move: the same data disclosure that satisfies a regulator is,
      rendered warmly, the most-shared feature in the app (Wrapped is literally
      a data export). Prototype "your data, legible and delightful" with real
      controls attached. Compliance becomes product, not a popup interruption.

98. **[SYNTHETIC]** Revolut: design the account-frozen experience: a user's salary is inside and compliance has locked the account pending review.
    - Trap: hiding behind "we can't say anything" (the real current experience,
      and why the question exists). AML rules genuinely limit disclosure, but
      silence plus a locked salary is how you make a lifelong detractor.
      Prototype the maximum-legal-transparency state: case status, hard
      timelines, what documents move it faster, essential-spend carve-outs
      where law allows. Name the tipping-off constraint; design to its edge.

99. **[SYNTHETIC — modeled on Bolt loop reports]** Bolt (Tallinn): win riders in a new European city where Uber arrived two years earlier and habits are set.
    - Trap: competing on generic discounts, which buy trials but not switches.
      City-level wedges decide this: scooter/ride bundling where Bolt has
      density, local payment rails, driver-supply moves that beat Uber ETAs on
      specific corridors. A strong run picks ONE city, names its structure, and
      prototypes the switch moment (price-comparison honesty at booking).
      Pan-European abstractions are the miss.

100. **[SYNTHETIC]** Vinted: make cross-border secondhand buying (Lithuania seller, French buyer) feel as safe as domestic.
     - Trap: assuming payments are the fear. Escrow is solved; the anxieties are
       sizing across country conventions, 10-day shipping silence, and
       who-pays-return-postage disputes. Prototype the cross-border listing
       view (size translation, landed-cost clarity, tracked-shipping states)
       and the dispute flow. The borderless feed is easy; the borderless
       return is the product.

101. **[SYNTHETIC]** DeepL: expand from translator to writing assistant for a German professional writing English emails all day, against free ChatGPT.
     - Trap: chasing ChatGPT's breadth. DeepL's wedge is the opposite: nuance
       fidelity for high-stakes bilingual professionals (tone register in
       German business culture, terminology consistency across a company's
       documents, data-residency trust). Prototype the in-flow email assist
       with a tone dial and a "this phrasing is unusually blunt in English"
       nudge. Breadth is their game; precision is yours.

102. **[SYNTHETIC]** Too Good To Go: help a first-time user get past the surprise-bag lottery anxiety ("what if it's all bread?").
     - Trap: breaking the model by adding item-level transparency. The surprise
       bag is not a bug; it is what makes unsold-inventory economics work for
       stores, and full menus would kill supply. Design inside the constraint:
       category odds ("usually 60% pastry"), streak-free ratings of past bags,
       first-bag guarantee. Candidates who prototype an itemized menu broke
       the business to fix the UX.

## Greenfield

103. **[SYNTHETIC]** Design a product that helps new managers run better 1:1s. (greenfield)
     - Trap: building an agenda-template tool. Templates are a commodity; every
       notes app has them. The differentiated wedge is what happens between 1:1s
       (the manager forgetting Tuesday's promise by Friday). Greenfield also means
       no existing UI to copy: interview-harness-builder must generate design-system.md from
       scratch, and candidates who skip that ship gray-box prototypes.

104. **[SYNTHETIC]** Design an app for coordinating care of an aging parent across siblings. (greenfield)
     - Trap: assuming goodwill. Sibling care coordination is loaded with guilt and
       uneven effort; a shared to-do list ignores the actual dynamics. Strong runs
       name the emotional guardrail (no shame mechanics, no public scoreboards of
       who visited) before proposing anything.

105. **[REAL — PMCurve prep bank (unattributed), 2026]** Build a habit tracker, then explain why yours would retain users when hundreds of habit trackers have not.
     - Trap: the second clause, which most candidates never address. A habit
       tracker is the single most-generated vibe-coding app; shipping the AI's
       default (grid of checkboxes, streak counter) proves you cannot exceed the
       tool. The differentiated angle must be named before prompting: a specific
       user, a specific failure mode of existing trackers, one mechanic that
       attacks it.

106. **[SYNTHETIC]** Design a product for the first 90 days after a layoff. (greenfield)
     - Trap: building a job-search tool on day one. The first weeks are triage
       (COBRA deadlines, severance math, filing for unemployment) tangled with
       identity shock; "update your resume!" on day 3 is tone-deaf. Sequence is
       the insight: prototype the stabilization phase with the job-search
       machinery deliberately deferred, and say why.

107. **[SYNTHETIC]** Design a product that helps renters get their security deposits back. (greenfield)
     - Trap: building for move-out week, when the evidence war is already lost.
       Deposits are won at move-IN (timestamped condition documentation) and
       held through tenancy (repair-request paper trail). Prototype the
       evidence locker plus the state-specific demand letter generator, and
       name the adversary: this is a product with an opponent, and the tenant needs an advocate as much as a user interface.

108. **[SYNTHETIC]** Design a tool for wedding planning where the couple has wildly different budgets in mind. (greenfield)
     - Trap: prototyping a checklist-and-vendors app and dodging the stated
       conflict. The question names the fight; the product is conflict
       infrastructure: private priority ranking before joint reveal, trade-off
       visualization ("the band costs 40 guest-dinners"), a decisions ledger.
       A Pinterest-board clone ignores the sentence the interviewer wrote.

109. **[SYNTHETIC]** Design a product for hourly shift workers to swap shifts without the group-text chaos. (greenfield)
     - Trap: building a marketplace and forgetting the manager. Every swap has a
       silent third party with veto power (overtime rules, skill coverage,
       labor law). A peer-to-peer board that ignores approval gets people
       fired. Prototype the swap flow with rule-checking built in ("this swap
       puts Maria into overtime, blocked") and one-tap manager sign-off.

110. **[SYNTHETIC]** Design a product that helps a solo consultant sound bigger than one person without lying. (greenfield)
     - Trap: the last three words. Fake team pages and "we" copy are the obvious
       dark-pattern answer, and the constraint bans them. The honest version
       sells solo as premium (direct access, no juniors) while fixing the real
       gaps that make solo feel small: response latency, professional ops
       (proposals, invoicing, status pages). Integrity constraint honored
       visibly, or the run fails on judgment.

## Curveballs

111. **[SYNTHETIC]** Meta: you have 30 minutes and the interviewer says "surprise me with something for Groups."
     - Trap: the open brief. No constraint means candidates burn 12 minutes choosing.
       The counter is to impose your own constraint fast ("I'll focus on group
       admins, they're the retention lever") and say it in one sentence. Deciding
       quickly IS the evaluation.

112. **[SYNTHETIC]** Any product above, but the interviewer hands you the solution in minute 2.
     - Trap: obedience. Building exactly what was handed to you reads as no judgment;
       refusing reads as unmanageable. The move is the redirect: accept, reframe
       against the user problem, and offer it as one of your three concepts.
       Practicing the redirect is the point; see references/scripts.md.

113. **[SYNTHETIC]** Uber: mid-run, the interviewer says "actually, make it work for drivers instead of riders." (pivot drill)
     - Trap: sunk cost. Candidates keep polishing the rider prototype for five more
       minutes. The scored behavior is the cutover: keep the harness, swap the user,
       re-issue one clean build prompt with all four elements. Under 60 seconds
       from pivot to new prompt is the bar.

114. **[SYNTHETIC]** Google Maps: improve the experience of navigating with kids in the car. (multi-context)
     - Trap: adding features to a driving screen. Anything demanding driver attention
       is a safety regression, and the interviewer is waiting for you to notice.
       Strong runs move the interaction off the drive (pre-trip setup, passenger
       mode, voice) and say the safety constraint before the first concept.

115. **[SYNTHETIC]** Your own current product: your CEO saw a competitor's AI feature and wants "that, but ours, by Friday." (internal politics)
     - Trap: the fake deadline becomes the spec. Cloning by Friday is the losing
       move and so is a flat no. The scored behavior is a scoped counter: prototype
       the thinnest honest version, state what Friday buys and what it costs, and
       put the real version behind one metric. Scored under Product Sense, Solution
       sub-dimension.

116. **[SYNTHETIC — modeled on real Meta follow-up reports]** Mid-build, the interviewer starts grilling: "Aren't you using more tokens than necessary? What about latency? Why not image generation?" (technical cross-examination drill)
     - Trap: bluffing depth you do not have, or freezing. Reported by candidates from
       Meta's AI round. The scored behavior is calibrated honesty: answer what
       you know ("I front-loaded context deliberately; iteration prompts stay
       short"), bound what you do not, and tie every technical answer back to a
       user-facing tradeoff. Never let the cross-examination stop the build;
       talk while the tool generates.

117. **[SYNTHETIC]** The prototyping tool errors out with 12 minutes left and your last working version is three prompts old. (tool-failure drill)
     - Trap: debugging in front of the interviewer. Fighting an opaque error for
       eight minutes is the silent fail everyone remembers. The scored behavior
       is the cutover call within 90 seconds: revert to the last working state,
       narrate what the broken increment would have shown, and finish the story
       on the working artifact. Recovery composure is a rubric line; treat the
       crash as the question.

118. **[SYNTHETIC]** Interviewer: "Your prototype looks great. What's wrong with it?" (self-critique drill)
     - Trap: false modesty ("the colors could be better") or defense. The question
       tests whether you can see AI output critically, the exact skill these
       rounds exist to measure. Strong answers name a structural gap (missing
       state, wrong seeded data, a flow that dodges the hard case) and what the
       next 30 minutes would fix, in priority order. Have this answer pre-loaded;
       it is asked constantly.

119. **[SYNTHETIC]** Interviewer: "How would you test whether this feature actually works, before and after launch?" (validation drill)
     - Trap: jumping to the A/B test. You cannot A/B what you have not derisked;
       the prototype in front of you IS the pre-launch instrument (five user
       sessions against the seeded flows this week). Then the launch design:
       one primary metric, one guardrail, holdout duration. Candidates who say
       "we'd A/B test it" and stopped there have named a tool instead of a test.

120. **[SYNTHETIC — modeled on Google India reports]** "Pick any feature of any product you use daily and rebuild your own version of it, in any vibe coding tool, right now." (open-tool drill)
     - Trap: picking your comfort product and over-scoping it. The reported
       Google India format is exactly this open. Choose small and stateful (a
       feature with 2-3 screens and one interesting edge case), say why it is
       interesting in one sentence, and budget minutes out loud. The choice
       itself is scored: rebuilding all of Instagram Stories is a scoping fail
       before the first prompt.

## Sample trap-dodge, 60 seconds each

Two openings from a plausible strong run, for calibration:

- LinkedIn (Q1): "Opening LinkedIn now. My Network tab is 100% new-connection
  suggestions; there is literally no surface for existing ties. That absence is
  the insight. User: mid-career operator, 900 connections, messages 5 a year.
  Problem: dormant ties decay silently. I'll sketch three concepts, then
  prototype a reconnect queue triggered by job changes." Product opened,
  parenthetical honored, scope set. Ninety seconds.

- Netflix (Q6): "Before proposing anything: Play Something exists, so randomness
  is solved. What I see browsing right now is that every row answers 'what is
  popular,' none answer 'what fits Tuesday 9pm, two tired adults, 45 minutes.'
  That is the gap I will build against." The trap named and stepped over in one
  breath.

After any run, grade against references/scorecard.md, run skills/taste/SKILL.md
on the artifact, and log which trap (if any) landed. Repeat questions only after
the full bank is exhausted once.

## Provenance notes

- Counts: 120 questions total. 11 tagged **[REAL]** (4 Meta via Prepfully and an
  IGotAnOffer candidate report; 1 Netflix homework and 2 prompt types via the
  Product Growth newsletter; 4 from the PMCurve published prep bank, which is
  prep material rather than a company report and is tagged accordingly).
  11 more are **[SYNTHETIC — modeled on real reports]** (Meta follow-up style
  and WhatsApp variant, Google India open-tool format, Netflix consumer focus,
  Kraken/Airwallex/Adobe/DataRobot/NBCUniversal/Bolt loop formats). The
  remaining 98 are **[SYNTHETIC]**, authored for this bank.
- Why so few verbatim real questions: this round is new (Meta's AI product
  sense round rolled out 2025-26; Google India, Microsoft, Netflix, Shopify
  reports are 2025-26). Candidates sign NDAs, and most public reports describe
  the FORMAT (30 min product sense + 30 min build in a Llama-based tool /
  Lovable / v0) rather than the exact prompt. What is well-attested: Meta's
  round exists and grills on tokens/latency/retrieval mid-build; Google India
  runs it for AI PM roles; Microsoft and Adobe have piloted it; Netflix and
  Stripe use homework-with-prototype formats; Shopify's COO has said PMs have
  "no excuse" not to prototype.
- Main sources: IGotAnOffer (Meta Product Sense with AI guide, PM vibe coding
  guide), Prepfully (Meta product-sense-with-AI guide), Product Growth /
  Aakash Gupta newsletter (vibe coding interview guide, AI PM interview guide
  2026, Google PM guide 2026), PMCurve newsletter, Exponent (Shopify, Meta
  guides), Blind threads (Meta loop change, Google vibe coding, Microsoft PM
  vibe coding), Lenny's Newsletter (prototyping practice context). Full URL
  list: references/question-bank-research-log.md.
- Caveat: all anonymous-forum and prep-site reports are paraphrased, second-hand,
  and unverified. Treat [REAL] tags as "reported," not "confirmed." Companies
  change prompts constantly, which makes the traps the durable part of this
  bank rather than the prompts themselves.
