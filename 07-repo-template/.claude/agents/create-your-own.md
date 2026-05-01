# Create Your Own Agent — Guided Prompt

This file contains a prompt to paste into Claude Code. It will walk you through building a custom agent step by step.

---

## The prompt

Copy everything between the triple backticks and paste it into Claude Code:

```
I want to create a new Claude Code agent for this project. Please walk me through it.

Ask me these questions one at a time and wait for my answer before continuing:

1. What task should this agent handle? Describe the job it should do.
2. When should this agent be triggered? What phrases would I use when I want it?
3. What should it always do first? (e.g., read CLAUDE.md, check a specific folder)
4. What are the main steps of its workflow?
5. What should it NEVER do? What are the guardrails?
6. What tools does it need? Options are: Read, Write, Edit, Glob, Grep, Bash, WebSearch, WebFetch. Pick only what it actually needs.
7. What model should it use? Haiku (faster, cheaper, good for simple tasks), Sonnet (default, balanced), or Opus (expensive, best for complex reasoning)?

After I answer all questions, write the agent file to `.claude/agents/` with a name we agree on.
Then show me what you created and explain each section.
```

---

## What to expect

Claude Code will ask you the questions above one at a time. Answer each one clearly. After the last answer, it will:

1. Write the agent file in `.claude/agents/your-agent-name.md`
2. Show you the file it created
3. Explain what each section does

---

## Editing your agent after creation

Once created, you can edit the agent file directly in VS Code. The key sections to tweak:

**`description:`** — These are the trigger phrases. Add more examples to make it trigger more reliably.

**Workflow steps** — If the agent is missing a step or doing steps in the wrong order, edit the numbered list.

**Never section** — Add guardrails as you discover edge cases where the agent behaves unexpectedly.

**`model:`** — If the agent is too slow, switch to `haiku`. If it's not good enough, switch to `opus`.

---

## Examples of useful custom agents

- **Weekly review agent** — reads your active-work doc, summarizes what got done, drafts next week's priorities
- **Onboarding agent** — reads the full knowledge base and produces an onboarding doc for a new team member
- **Changelog agent** — reads recent git commits and generates a CHANGELOG entry
- **Data validator agent** — reads a data schema and validates a CSV against it before processing
- **Deploy checklist agent** — reads a deploy runbook and walks you through each step interactively
