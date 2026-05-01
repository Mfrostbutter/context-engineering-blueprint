# BOOTSTRAP — Initialize This Project

Paste this entire file's contents into Claude Code to scaffold your project. Claude Code will ask you questions and set everything up.

---

## Prompt

```
I'm initializing a new project using the context-engineering-blueprint template.
Please walk me through setup.

First, ask me these questions (one at a time):
1. What is this project? Describe it in 2-3 sentences — what does it do, what's the goal?
2. What are your 3-5 most important rules for this project? (Think about: security, file management, code quality, documentation.)
3. What folders do you need beyond the defaults (src/, prototypes/, docs/, knowledge/, Archive/)? Or should we use the defaults as-is?
4. What's the first thing you're going to work on in this project?

Then do the following:

1. Update CLAUDE.md with my project description and rules (fill in all the <!-- FILL IN --> sections)
2. Update README.md with my project description
3. If I mentioned any additional folders, create them
4. Create knowledge/decisions/YYYY-MM-DD-initial-setup.md documenting the key decisions I mentioned
5. Create a .env.example file if my project will need any credentials (ask me what credentials it needs)
6. Run: git add . && git commit -m "chore: init project from context-engineering-blueprint"

After setup, show me a summary of what you created and what I should do next.
```

---

## What Claude Code will do

Working through the questions above, Claude Code will:

- Fill in your `CLAUDE.md` with your project description and rules
- Update your `README.md`  
- Create any additional folders you need
- Write your first knowledge base entry documenting the setup decisions
- Create a `.env.example` if you need credentials
- Make your initial git commit

Total time: about 5 minutes.

---

## After bootstrap

1. Open `CLAUDE.md` and read it — edit anything that feels off
2. Open `knowledge/decisions/` and check the entry Claude Code created — add anything it missed
3. Open `07-repo-template/.claude/agents/` (if you copied the template) — read the available agents
4. Start working. Tell Claude Code what you want to build or fix.

---

## Troubleshooting

**Claude Code can't find the CLAUDE.md template:**
Make sure you're running `claude` from inside the project directory (not a parent folder).

**The questions don't seem relevant to my project:**
Just answer what you can and tell Claude Code what to skip. The prompts are guides, not requirements.

**I want to redo the setup:**
Tell Claude Code: "Let's redo the CLAUDE.md — my project has changed. Ask me the setup questions again."
