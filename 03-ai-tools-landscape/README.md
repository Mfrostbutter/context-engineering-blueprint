# 03 — AI Tools Landscape

There's a lot of AI tooling out there. Before going deeper, it's worth understanding the landscape — what each category of tool does well and when you'd use it.

This section covers:

- [Web Chat Tools](./web-chat-tools.md) — Claude.ai, ChatGPT, Gemini — what they're good for and their limits
- [IDE-Based AI Tools Overview](./ide-tools-overview.md) — Claude Code, Cursor, Cline, Copilot — quick comparison

---

## The two modes of working with AI

### Mode 1: Web chat
You open a browser, type a question, get an answer. The AI has no context about your work unless you paste it in. When you close the tab, the conversation is gone.

**Best for:**
- Quick questions
- Drafting documents
- Explaining concepts
- Tasks that don't need file access

**Limitations:**
- No memory between sessions
- You have to paste context every time
- Can't read your files, run your code, or check your codebase
- No integration with your tools

### Mode 2: IDE-based AI (agentic)
You open VS Code or a terminal, the AI reads your files, runs commands, edits code, and commits changes. It has access to your project context — including CLAUDE.md — so it doesn't start from scratch every session.

**Best for:**
- Coding and debugging
- Large file operations (reading, editing, creating)
- Multi-step tasks ("set up this project", "review all changed files", "create a new agent")
- Work that should be tracked in Git

**Limitations:**
- Requires setup (VS Code, API key or subscription)
- More powerful = more responsibility (the AI can actually change things)
- Not useful for quick one-off questions

---

## Which should you use?

Use web chat for **thinking and drafting**. Use IDE-based AI for **doing**.

Most people who've moved to IDE-based AI still use web chat for quick research, brainstorming, and things that don't need file access. The tools are complementary.

---

## What's coming

This repo is focused on moving you toward IDE-based AI. Section 04 walks through setup. But you don't have to abandon web chat — you'll just have more options.

Next: [Web Chat Tools](./web-chat-tools.md)
