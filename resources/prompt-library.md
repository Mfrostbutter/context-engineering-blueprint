# Prompt Library

Reusable prompt starters for common tasks. These work in both web chat (Claude.ai, ChatGPT) and IDE-based tools (Claude Code).

Copy and modify for your specific situation.

---

## Project setup and context

**Initialize a new project:**
```
I'm starting a new project. Here's what it is:
[describe project in 2-3 sentences]

Help me:
1. Create a CLAUDE.md with mission, non-negotiables, and directory structure
2. Set up a folder structure appropriate for this project
3. Create a knowledge/ folder with README explaining what belongs there
4. Make an initial git commit
```

**Review and improve my CLAUDE.md:**
```
Read my CLAUDE.md and tell me:
1. What's missing that would help you work more effectively in this project?
2. Are any rules too vague to actually enforce?
3. What should I add to the directory structure section?
```

---

## Knowledge management

**Capture a decision:**
```
I just made a decision about this project and want to capture it. 
The decision: [what was decided]
The reason: [why]
The alternatives I considered: [what else I looked at]

Write a decision file to knowledge/decisions/[today's date]-[short-description].md
```

**Capture a learning:**
```
I just figured out something non-obvious and want to capture it for future reference.
The problem: [what was confusing or broken]
The solution: [what fixed it]

Write a learning to knowledge/learnings/[topic-name].md
```

**Search my knowledge base:**
```
Search knowledge/ for anything relevant to [topic]. 
Summarize what we already know before I start working on this.
```

---

## Code review and quality

**Review before committing:**
```
Review the files I've changed since my last commit.
Check for: hardcoded credentials, logic errors, missing error handling, violations of CLAUDE.md rules.
Organize findings as: blocking / important / minor.
```

**Explain this code:**
```
Read [file path] and explain what it does to someone who hasn't seen it before.
Focus on: what problem it solves, how it works at a high level, any non-obvious design choices.
```

**Refactor for readability:**
```
Refactor [file path] to be more readable. 
Constraints: don't change behavior, don't add new dependencies, keep the same function signatures.
```

---

## Documentation

**Write a runbook:**
```
Write a runbook for [process/script/system].
Audience: someone who has never done this before.
Include: prerequisites, step-by-step instructions, how to verify it worked, what to do if something goes wrong.
Save to docs/[name]-runbook.md
```

**Update docs after a change:**
```
I just changed [what changed]. 
Read the existing documentation in docs/ and update anything that's now out of date.
List what you changed.
```

**Create a README for this folder:**
```
Read all the files in [folder path] and write a README.md that explains:
- What this folder contains
- What each file does
- How they relate to each other
- Any important notes for someone working in this folder
```

---

## Git and GitHub

**Write a commit message:**
```
Look at my staged changes (git diff --staged) and write a commit message.
Format: [type]: [short description]
Types: feat (new feature), fix (bug fix), docs (documentation), chore (maintenance), refactor
Keep it under 72 characters. Focus on what changed and why.
```

**Summarize recent work:**
```
Read git log --oneline -20 and summarize what's been worked on recently.
Organize by theme, not by commit.
```

**Write a PR description:**
```
I'm about to open a pull request. Read the diff between my branch and main.
Write a PR description with:
- Summary (2-3 sentences)
- What changed (bullet list)
- How to test it
- Any risks or things to watch out for
```

---

## Automation and n8n

**Design a workflow:**
```
I want to build an automation workflow that does the following:
[describe in plain English]

I'm using [n8n/Make/Zapier].
Break it down into steps, identify the nodes/modules needed, and flag any issues.
```

**Improve an existing workflow:**
```
I have a workflow that does [what it does]. 
It works but feels inefficient.
Suggest: where I could add AI to add value, where I can reduce the number of steps, 
any edge cases I'm probably not handling.
```

---

## Research and decision-making

**Research before deciding:**
```
I need to decide between [option A] and [option B] for [purpose].
Research both options and give me:
- What each option is good at
- Where each falls short
- Which you'd recommend for my situation and why
My situation: [brief context]
```

**Summarize a long document:**
```
Read [file or paste document] and give me:
- The 3 most important things to know
- Any action items or decisions required
- Anything that seems concerning or worth flagging
Keep the summary under 200 words.
```

**Prepare for a meeting:**
```
I have a meeting about [topic] with [who].
Read my project context and give me:
- 2-3 sentences of background
- 3-5 key points to raise
- Any decisions that need to come out of this meeting
- 3 questions to ask
```
