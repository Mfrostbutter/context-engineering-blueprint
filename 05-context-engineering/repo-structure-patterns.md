# Repo Structure Patterns

How you organize your files determines what the AI can do with them. Good structure is invisible — it just works. Bad structure means constant context re-explanation.

---

## The graduation model

The most important pattern: separate experiments from production.

```
my-project/
├── src/          ← production-ready work
├── prototypes/   ← experiments
└── Archive/      ← retired work
```

**Rule:** Nothing in `src/` imports from `prototypes/`. Experiments stay experiments until you decide to graduate them.

**Why it matters for AI:** When you ask Claude Code to "improve the main script," it knows to look in `src/`, not `prototypes/`. When you say "I want to try something new," it knows to put it in `prototypes/`.

---

## The knowledge folder

A `knowledge/` directory is your extended knowledge base — a collection of markdown files the AI reads as context.

```
knowledge/
├── README.md            ← what goes in each subfolder
├── decisions/           ← architecture and project decisions
│   └── 2026-05-01-chose-python-over-nodejs.md
├── learnings/           ← hard-won lessons and gotchas
│   └── csv-encoding-issues.md
└── contacts/            ← people, roles, responsibilities
    └── vendors.md
```

**Key principle:** When you learn something the AI will need later, write it in `knowledge/`. It becomes permanent context — the AI reads it automatically because CLAUDE.md points to this folder.

Contrast with: telling the AI the same thing every session. That's not context engineering; that's repetition.

---

## Per-module documentation (the runbook pattern)

Every significant component of your project should have its own README or guide.

```
src/
├── export-processor/
│   ├── README.md    ← what this does, how to run it, known issues
│   └── main.py
├── email-sender/
│   ├── README.md
│   └── send.py
```

**Why it matters:** CLAUDE.md points to these READMEs instead of duplicating content. When you're working on `export-processor`, Claude Code reads its README and knows the context without you repeating it.

---

## Load-on-demand references

CLAUDE.md should be short. Detailed documentation lives in `docs/` and gets pointed to from CLAUDE.md.

**In CLAUDE.md:**
```markdown
## References
- Export processor: `src/export-processor/README.md`
- Data schema: `docs/data-schema.md`
- Deploy steps: `docs/deploy.md`
```

**Not in CLAUDE.md:**
```markdown
The export processor reads CSV files from the exports/ folder. The schema has columns: id, name, email, 
created_at. The date format is ISO 8601. You need to handle encoding errors because some files come 
in Windows-1252 encoding. The deploy process involves...
```

Keep CLAUDE.md as a table of contents. Put the detail in dedicated docs.

---

## Active work tracking

A single `knowledge/active-work.md` (or `docs/active-work.md`) that tracks what's in progress:

```markdown
# Active Work — updated 2026-05-01

## In progress
- [ ] Add error handling to export processor (started 2026-04-28)
- [ ] Document the email send logic

## Blocked
- [ ] Migrate to new CSV format (waiting on vendor docs)

## Done recently
- [x] Fixed encoding issue with Windows-1252 files (2026-04-30)
```

When you start a new Claude Code session, the AI reads this and knows where things stand — no re-explanation needed.

---

## The .env pattern for secrets

Never put credentials in your code or in CLAUDE.md. Always use environment files.

```
my-project/
├── .env              ← actual credentials (NEVER commit this)
├── .env.example      ← template showing what variables are needed (commit this)
└── .gitignore        ← must include .env
```

**`.env.example`:**
```
OPENAI_API_KEY=your-key-here
DATABASE_URL=postgresql://user:password@host:5432/dbname
SMTP_PASSWORD=your-password-here
```

**`.gitignore`:**
```
.env
*.env.local
```

**CLAUDE.md reference:**
```markdown
## Configuration
All credentials via .env. See .env.example for required variables. Never hardcode.
```

---

## Summary: the five patterns

1. **Graduation model** — `prototypes/` for experiments, `src/` for production, never mix
2. **Knowledge folder** — `knowledge/` is your extended knowledge base, structured and AI-readable
3. **Per-module runbooks** — every significant component gets its own README
4. **Load-on-demand refs** — CLAUDE.md points to docs, doesn't contain them
5. **Secrets in .env** — credentials never in code, CLAUDE.md, or Git

Apply these five patterns and you'll spend more time working and less time re-explaining.
