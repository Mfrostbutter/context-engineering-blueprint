# What to Capture

The knowledge folder only works if you put things in it. Here's a framework for deciding what's worth writing down.

---

## The test: would this save someone an hour?

When you learn something, ask: "If a colleague was starting this task cold, would this information save them an hour of research or trial and error?"

If yes, write it down.

---

## What's worth capturing

### Decisions with non-obvious rationale
When you make a choice and the reason isn't obvious from the code or docs — write it down.

Examples:
- "We chose vendor X over vendor Y because Y's API has no bulk endpoint"
- "We don't use the built-in export feature because it silently drops rows with null values"
- "We run this script as a scheduled task, not a webhook, because the source system's webhook delivery is unreliable"

If someone could look at your project and say "why did they do it this way?" — that's a decision worth capturing.

### Gotchas and edge cases
Things that look simple but aren't. Anything that bit you.

Examples:
- "The vendor's CSV files use Windows-1252 encoding, not UTF-8"
- "The API rate limit is per-minute not per-day — bursting 100 requests breaks authentication"
- "This field says 'optional' in the docs but the system throws a 500 if it's null"

### Non-obvious setup steps
Things that took time to figure out that aren't in the official docs.

Examples:
- "You need to run `npm install --legacy-peer-deps` or it fails on Windows"
- "The dev environment requires setting this env var or the auth middleware returns 401 on all routes"
- "The first time you run this, you need to manually create the database schema — it doesn't auto-migrate"

### Vendor and contact context
Who to call when things break. What to expect from each vendor. Reliability notes.

Examples:
- "Support tickets go to this email, not the main support form — the form is never monitored"
- "Their system has scheduled maintenance every Sunday 2-4am EST — don't schedule jobs then"
- "Account rep is [name], direct line is [X] — use for escalations, not general questions"

### What you tried and why it didn't work
Negative knowledge is underrated. If you spent two hours trying approach X before realizing it doesn't work, write that down so no one (including the AI) repeats it.

---

## What's NOT worth capturing

**Things that are in official docs.** Don't copy-paste docs into your knowledge folder. Link to them instead.

**Temporary workarounds you plan to remove.** If it's a short-term hack, put a TODO comment in the code and a note in the commit message. Knowledge folder is for things that will still be true in six months.

**Step-by-step procedures that are already documented.** Runbooks belong in `docs/`, not `knowledge/`. The knowledge folder is for context that helps you understand and navigate the project — not step-by-step instructions.

**Personal to-dos and task lists.** Use a task manager or GitHub Issues for tracking work. The knowledge folder is for reference, not tasks.

---

## Building the habit

The hardest part isn't knowing what to capture — it's doing it consistently.

**Capture immediately, clean up later.** The moment you figure something out, write a rough note. Don't wait until you have time to write it cleanly. A rough note exists; a perfect note in your head doesn't.

**One file per topic.** Don't create one massive "notes.md." Separate files are easier to find, easier to reference in CLAUDE.md, and easier for Claude Code to search.

**Date decisions, not learnings.** Decision files benefit from dates (they get outdated, decisions change). Learning files don't need dates — the content matters more than when you wrote it.

**Review quarterly.** Every few months, read through your knowledge folder. Delete or archive things that are no longer true. Update things that have changed. Keep it current.

---

## Seeding your knowledge folder

When you set up a new project, don't start with an empty knowledge folder. Immediately write down:

1. `decisions/YYYY-MM-DD-initial-architecture.md` — the key choices you made when setting up
2. `learnings/environment-setup-notes.md` — anything that wasn't obvious during setup
3. `contacts/key-contacts.md` — who the stakeholders are and how to reach them

These three files will be useful for the entire life of the project.
