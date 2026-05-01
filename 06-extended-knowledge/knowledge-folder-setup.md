# Knowledge Folder Setup

The `knowledge/` folder is a markdown-based extended knowledge base that Claude Code can read as context. No database, no vector store — just organized text files.

---

## Structure

```
knowledge/
├── README.md            ← what goes in each subfolder (important: Claude Code reads this)
├── decisions/           ← why you made key choices
│   └── YYYY-MM-DD-decision-name.md
├── learnings/           ← hard-won lessons and gotchas
│   └── topic-name.md
└── contacts/            ← people, roles, vendors, responsibilities
    └── vendors.md
```

---

## The README.md in knowledge/

Create a `knowledge/README.md` that explains what the folder contains. This is what Claude Code reads to understand your knowledge base.

```markdown
# Knowledge Base

Context that persists across sessions. Claude Code should read this before making decisions.

## decisions/
Key architectural and process decisions with rationale. Check here before making
significant changes to understand why things are the way they are.

## learnings/
Hard-won lessons, gotchas, and non-obvious information discovered during this project.
Check here before working on a topic — someone may have already figured out the tricky parts.

## contacts/
Vendor contacts, team members, roles, and responsibilities. Use when you need to know
who to reach for something or what a vendor's capabilities are.
```

---

## decisions/ — capturing why

Decision files explain why you made a choice. The "why" is what disappears from memory and what the AI needs most.

**Naming:** `YYYY-MM-DD-short-description.md` — the date makes it easy to see when a decision was made, which matters when things change.

**Template:**
```markdown
# Decision: [what was decided]
Date: [YYYY-MM-DD]

## What we decided
[One sentence.]

## Why
[The reasons. What alternatives did you consider? What made this the right choice?]

## Constraints that drove this
[Requirements, vendor limits, time pressure, technical constraints that shaped the decision.]

## What to watch for
[What could make this decision wrong in the future? When should it be revisited?]
```

**Example:**
```markdown
# Decision: Use CSV export instead of API integration
Date: 2026-04-15

## What we decided
Pull data from the vendor system via daily CSV export rather than their REST API.

## Why
The vendor API has a 100-request-per-minute rate limit and inconsistent pagination.
CSV exports are reliable, complete, and can be scheduled without API key management.

## Constraints that drove this
Vendor API documentation is incomplete. Export schedule is set to run at 2am daily.

## What to watch for
If we need real-time data in the future, CSV won't work. Also watch for vendor
changing the CSV schema — we have no schema versioning notification.
```

---

## learnings/ — capturing gotchas

Learnings are the things that would have saved you an hour if you'd known them sooner.

**Template:**
```markdown
# [topic name]

## The problem
[What went wrong or what was confusing.]

## What we learned
[The actual answer. Be specific.]

## How to handle it
[What to do when you encounter this. Steps, commands, anything concrete.]

## References
[Links to docs, Stack Overflow answers, or vendor knowledge base articles that helped.]
```

**Example:**
```markdown
# CSV encoding issues — Windows-1252

## The problem
Files from the legacy system come in Windows-1252 encoding, not UTF-8. Python's
csv.reader crashes on any file with special characters (em dashes, accented letters).

## What we learned
You must specify the encoding explicitly when opening the file. Python defaults to
UTF-8 and will throw UnicodeDecodeError on the first special character.

## How to handle it
```python
with open(filepath, encoding='windows-1252', errors='replace') as f:
    reader = csv.reader(f)
```
The `errors='replace'` means bad characters become '?' instead of crashing.

## References
- Stack Overflow: https://stackoverflow.com/questions/17912307/...
- Python docs: https://docs.python.org/3/library/codecs.html#standard-encodings
```

---

## contacts/ — capturing people and vendors

Contacts is not a phone book. It's context about who does what and what to expect from them.

**Template:**
```markdown
# [Vendor / Person Name]

## What they do for us
[One sentence about the relationship.]

## Key contacts
- [Name]: [Role] — [email or how to reach them]

## What they provide
[What we use from them: API, export, service, hardware, etc.]

## Known quirks and limits
[Rate limits, format quirks, reliability notes, anything the AI should know before working with their data.]

## Escalation path
[If something breaks, what's the process? Support ticket? Direct call?]
```

---

## Adding CLAUDE.md references

Add this to your CLAUDE.md:
```markdown
## References
- Knowledge base: `knowledge/README.md`
- Key decisions: `knowledge/decisions/`
- Learnings and gotchas: `knowledge/learnings/`
- Vendor and team contacts: `knowledge/contacts/`
```

Once that's in CLAUDE.md, Claude Code reads your knowledge folder context automatically at the start of every session.
