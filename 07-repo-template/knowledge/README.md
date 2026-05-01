# Knowledge Base

Context that persists across sessions. Claude Code reads this before making decisions.

---

## What belongs here

**decisions/** — Key choices made in this project, with rationale. Check here before making significant changes. Understanding *why* things are the way they are prevents repeating past mistakes.

**learnings/** — Hard-won lessons, gotchas, and non-obvious information discovered during this project. If something took you an hour to figure out, it belongs here so the next person (or the AI) figures it out in seconds.

**contacts/** — Vendors, team members, and stakeholders — who they are, what they provide, and how to reach them. Especially useful for capturing reliability notes and escalation paths.

---

## How Claude Code uses this

When `CLAUDE.md` references this folder, Claude Code reads it at the start of each session. This means:
- The AI knows your past decisions and won't suggest approaches you've already rejected
- The AI knows your gotchas and won't repeat mistakes you've already made
- The AI knows your contacts and can give relevant context when working with vendor data

---

## How to add entries

**Decisions:** Create `decisions/YYYY-MM-DD-short-description.md`
Template: What was decided, why, what alternatives were considered, what to watch for.

**Learnings:** Create `learnings/topic-name.md`
Template: The problem, what was learned, how to handle it, references.

**Contacts:** Add to `contacts/vendors.md` or create `contacts/person-name.md`
Template: Who they are, what they provide, known quirks, escalation path.

---

## Keeping it current

- Date decision files — decisions change, and dates help you know when to revisit
- Delete or archive learnings that are no longer true
- Update contacts when people change roles or you find better escalation paths
