# Integrating with the Job Search OS

This harness runs standalone, but it gets meaningfully smarter inside Aakash's
Job Search OS (the Claude Code job search operating system). The OS already
knows who you are, where you're applying, and how your search is going. That
is exactly the data mock calibration wants and never has.

When the user says "integrate with my job search OS", "plug this into my job
search setup", or similar, follow this sequence.

## Step 1 — Find it

Ask for the path if it isn't obvious, or look for the usual signs in nearby
folders: a resume file, an applications tracker (spreadsheet or markdown
table), company research notes, outreach templates, a CLAUDE.md that talks
about job searching. Confirm what you found in one line before reading
deeper: "Found your job search OS at ~/job-search with a tracker and 4
company folders. Using it?"

## Step 2 — Place the harness

Two options, pick by how the user works:

- **Nested** (default): move or symlink this folder inside the OS, e.g.
  `job-search-os/prototyping-interview-harness/`. One workspace, one session,
  the OS's CLAUDE.md loads alongside this one.
- **Sibling**: keep the folders separate and add one line to the OS's
  CLAUDE.md: "For prototyping interview prep, read
  ../prototyping-interview-harness/CLAUDE.md." Cleaner when the user shares
  the OS folder with a coach.

Either way, add the reverse pointer here so a session started in this folder
knows the OS exists.

## Step 3 — Wire the data both directions

**Read from the OS** (this is where integration earns its keep):

| OS data | Feeds |
|---|---|
| Applications tracker: companies, stages, dates | Mock calibration picks the right company and format, and knows the interview date without asking |
| Resume / background | Question difficulty pitched to their level; debriefs reference their actual experience |
| Company research notes | context.md for that company's product gets a head start |
| Recruiter emails / interview confirmations | Round length and format, so calibration never assumes 30 minutes |
| Past interview notes or transcripts | interview-grader scores them; the next mock aims at what actually went wrong |

**Write back to the OS:**

- `practice-log.md` lives in the OS (next to the tracker), so mock scores sit
  beside application stages and the user sees readiness per company.
- After a graded mock or a graded real round, add one line to the tracker
  row for that company: date, three-area scores, biggest lever.
- The interview-day folder (interview-harness-builder's final step) gets
  built inside the OS's folder for that company, next to its research notes.

## Step 4 — Confirm the calibration loop

Run one line past the user to prove the integration is live: "Next mock will
calibrate from your tracker: Meta, AI PM, round on Aug 14, format 30+30,
weak spot per your last practice log: time management. Sound right?"

That sentence is the whole point of integrating. If the harness can't say it,
the wiring isn't done.

## Boundaries

- Read only what the calibration needs. Say what was read, every time, in one
  line. Never quietly mine the OS.
- Job search data never leaks into interview artifacts: nothing from the
  tracker, resume, or emails appears in prototypes, PRDs, or the
  interview-day folder. The sanitization pass in
  `skills/interview-harness-builder/SKILL.md` checks for this explicitly.
- If the OS and this harness give conflicting instructions (writing style,
  output rules), this harness wins inside interview work, the OS wins
  everywhere else.
