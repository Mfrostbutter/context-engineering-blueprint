# n8n

n8n (pronounced "n-eight-n") is an open-source workflow automation platform. It has 400+ integrations, built-in AI nodes, and can be self-hosted for free or used via cloud.

It's the most powerful option in this space and the one most worth learning for anyone doing serious automation work.

---

## What it is

A visual workflow builder. You drag and drop "nodes" onto a canvas and connect them. Each node represents an action or trigger — "when a new email arrives," "call the Claude API," "write to Google Sheets," "send a Slack message."

The result is a visual workflow you can see, edit, test, and share.

---

## Getting started

**Option A: n8n Cloud (recommended for beginners)**
1. Go to https://n8n.io/cloud
2. Sign up — free tier includes 5 active workflows and 2,500 executions/month
3. No installation required

**Option B: Self-hosted (free, more control)**
If you have Docker installed:
```bash
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
```
Then open http://localhost:5678 in your browser.

Full self-host docs: https://docs.n8n.io/hosting/

---

## Key concepts

**Trigger nodes** — What starts the workflow. Examples:
- Schedule Trigger: run at 9am every Monday
- Webhook Trigger: run when an external service sends an HTTP request
- Email Trigger: run when a new email arrives matching a filter
- Manual Trigger: run when you click a button (good for testing)

**Action nodes** — What the workflow does. Examples:
- Send Email
- Write to Google Sheets
- Post to Slack
- Call an HTTP API
- Run a code snippet (JavaScript or Python)

**AI nodes** — Built-in support for AI operations:
- "AI Agent" node: full agent with tool use
- "Basic LLM Chain": send text to Claude/GPT and get a response
- "Text Classifier": route items based on AI classification
- "Summarize": extract a summary from a document

**Credentials** — Securely stored connections to external services (your Claude API key, Gmail account, Slack workspace, etc.). Set up once, reuse everywhere.

---

## Connecting Claude to n8n

1. In n8n, go to Credentials → Add Credential
2. Search for "Anthropic"
3. Add your Claude API key
4. In any workflow, add an "Anthropic Chat Model" node and select your credential

Now any AI Agent or LLM Chain node can use Claude as its brain.

---

## Workflow example: email summarizer

```
[Email Trigger: new email in inbox]
    ↓
[Anthropic: summarize the email in 2 sentences]
    ↓
[Slack: post summary to #email-triage channel]
```

Build this in about 15 minutes by:
1. Creating a new workflow in n8n
2. Adding an Email Trigger node (configure with your email account)
3. Adding an Anthropic Basic LLM Chain node (prompt: "Summarize this email in 2 sentences: {{$json.text}}")
4. Adding a Slack node (configure with your Slack workspace)
5. Activating the workflow

---

## Saving and sharing workflows

n8n exports workflows as JSON files. To version-control them:
1. Click the workflow's name → "Download"
2. Save the JSON file in your project's `infra/n8n-workflows/` folder
3. Commit it to Git

This means your workflows are backed up, version-controlled, and shareable with teammates.

---

## Resources

**Official docs:** https://docs.n8n.io
**Official YouTube:** https://www.youtube.com/@n8n-io
**Community forum:** https://community.n8n.io
**Template library:** https://n8n.io/workflows (pre-built workflows you can import)
**Course:** n8n has a free beginner course at https://docs.n8n.io/courses/

---

## What n8n is NOT good for

- Very high-volume processing (thousands of operations per second) — use a real queue system
- Complex business logic that requires real software architecture
- Replacing a developer entirely — it's a tool, not a replacement for judgment
