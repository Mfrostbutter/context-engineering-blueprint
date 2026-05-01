# Obsidian Integration

Obsidian is a free markdown note-taking app that works on your local files — no cloud sync required (though sync is available). It's a popular tool for personal knowledge management and pairs naturally with Claude Code.

---

## Why Obsidian + Claude Code works well

Both tools work with plain markdown files on your filesystem. There's no conversion, no export, no sync setup needed. Obsidian reads your `knowledge/` folder as a vault. Claude Code reads the same files as context. One set of files, two powerful tools on top.

---

## Option A: Use knowledge/ as your Obsidian vault

1. Download Obsidian at https://obsidian.md (free)
2. Open Obsidian → "Open folder as vault"
3. Select your project's `knowledge/` folder
4. Done — Obsidian now shows your knowledge folder with its graph view, search, and editor

**Result:** You write notes in Obsidian's editor, they save as markdown files in `knowledge/`, and Claude Code reads them automatically.

---

## Option B: Use a standalone Obsidian vault and reference it from CLAUDE.md

If you already have an Obsidian vault elsewhere (e.g., `~/Documents/MyVault`), you can point CLAUDE.md to it:

```markdown
## References
- Personal knowledge base: `~/Documents/MyVault/work-notes/`
```

Claude Code can read any path on your filesystem that you point it to. The vault doesn't have to live inside your project.

**Caveat:** Paths with `~` work on Mac/Linux but may need to be absolute paths on Windows (`C:\Users\username\Documents\MyVault\`).

---

## Recommended Obsidian plugins for this workflow

All plugins are free and available in Obsidian's community plugin browser.

**Templater**
Creates templates for new notes. Use it to auto-populate the decision template, learning template, or contact template when you create a new file in those folders.

**Dataview**
Turns your notes into a queryable database. You can create a "decisions dashboard" that lists all decisions sorted by date, or a "open questions" view that shows all notes tagged with `#open-question`.

**Git (Obsidian Git plugin)**
Automatically commits and pushes your Obsidian vault to Git. Set it to commit every 30 minutes and your knowledge base is automatically version-controlled.

---

## Workflow: capturing a learning

1. You discover something non-obvious while working
2. Open Obsidian (or just create a file in `knowledge/learnings/` directly)
3. Write a quick note: what the problem was, what the solution is
4. Save — it's now in `knowledge/learnings/`
5. Next time you work in this project, Claude Code reads it automatically

The note doesn't have to be perfect. A rough note that's there is worth more than a perfect note that doesn't exist.

---

## Workflow: capturing a decision

This is more important than it seems. Six months from now you'll ask "why did we do it this way?" If the decision is in `knowledge/decisions/`, the AI can answer. If it isn't, you're starting from scratch.

After any significant decision:
1. Create `knowledge/decisions/YYYY-MM-DD-brief-description.md`
2. Fill in: what was decided, why, what alternatives were considered
3. Commit it

---

## What Obsidian doesn't need to do

You don't need Obsidian's graph view, backlinks, or any advanced features to get value from this workflow. The core value is:
- A good editor for markdown files
- Search across all your notes
- A way to see everything in one place

If you prefer VS Code's markdown editor, use that. The files are the same either way.
