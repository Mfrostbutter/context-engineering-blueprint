# 08 — Automation Platforms

Context engineering makes AI smarter in your projects. Automation platforms make AI useful across your business — connecting the tools you already use, running workflows without manual intervention, and scaling what would otherwise take hours of clicking.

This section covers the platforms that make automation accessible without writing code.

---

## The idea

Think of automation platforms as pipes that connect tools. When something happens in one tool (a new email, a form submission, a scheduled time), the platform triggers actions in other tools (update a spreadsheet, send a Slack message, create a task, call an AI model).

When you connect AI to these pipes, you get workflows that:
- Summarize incoming emails and route them
- Process data and generate reports automatically
- Respond to customer inquiries with AI-drafted messages
- Monitor systems and alert on anomalies
- Run nightly analysis and email results

All without writing Python or managing servers.

---

## What's in this section

- [n8n](./n8n.md) — The most powerful option; self-host for free or use cloud
- [Make and Zapier](./make-zapier.md) — Comparison of the two most popular no-code platforms
- [Example Workflows](./example-workflows.md) — 5 real workflows you can build as a beginner
- [Resources](./resources.md) — YouTube, docs, communities for going deeper

---

## Which platform should you start with?

| If you... | Start with |
|---|---|
| Want maximum power and don't mind a small learning curve | n8n |
| Want the simplest possible setup with a great free tier | Make |
| Need to connect the most possible apps with minimal setup | Zapier |
| Are already in the Google / Workspace ecosystem | Make or Zapier |
| Want to self-host and control your data | n8n |

If you're unsure, start with **n8n cloud** (n8n.io/cloud). Free tier for up to 5 active workflows. No server setup required.

---

## The AI + automation stack

The highest-leverage setup for most people:

1. **Claude Code** — for project-level work, coding, documentation, knowledge management
2. **n8n (or Make)** — for cross-tool automation and recurring workflows
3. **Claude API or Claude.ai** — as the AI brain inside your n8n workflows

You don't need all three to start. Pick one and go.
