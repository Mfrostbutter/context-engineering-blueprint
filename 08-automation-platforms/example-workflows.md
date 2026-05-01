# Example Workflows — 5 Beginner-Friendly Automations

These are real, buildable workflows. Each one is achievable in under an hour with n8n, Make, or Zapier.

---

## 1. Email summarizer and Slack router

**What it does:** When a new email arrives, Claude summarizes it in 2 sentences and posts it to a Slack channel with a link to the original.

**Why it's useful:** Stop reading every email immediately. Scan Slack summaries instead and only open the ones that need action.

**Trigger:** New email in Gmail/Outlook  
**Steps:**
1. Get the email subject, sender, and body
2. Send to Claude: "Summarize this email in 2 sentences. Flag if action is needed."
3. Post to Slack: `*From:* {sender} | *Subject:* {subject}\n{claude_summary}\n<{email_link}|Open email>`

**Build in:** n8n (use Email Trigger + Anthropic node + Slack node) or Make (Gmail + HTTP + Slack)

---

## 2. Form submission processor

**What it does:** When someone submits a form (Google Form, Typeform, etc.), save their response to a Google Sheet, send them a confirmation email, and notify your team in Slack.

**Why it's useful:** Eliminates the manual copy-paste-notify workflow that happens after every form submission.

**Trigger:** New form submission  
**Steps:**
1. Extract the form fields
2. Append a row to Google Sheets with the submission data
3. Send a confirmation email to the submitter
4. Post to Slack: "New submission from {name}: {summary}"

**Optional AI step:** Add a Claude node between steps 1 and 2 to classify the submission (e.g., "Is this a sales inquiry, support request, or partnership inquiry?") and route to different Slack channels.

**Build in:** Zapier (cleanest for this use case — native Typeform, Sheets, Gmail, Slack integrations)

---

## 3. Scheduled weekly digest

**What it does:** Every Monday morning, pull data from one or more sources, have Claude summarize the week's activity, and email you a digest.

**Why it's useful:** Replace manual weekly review with an automated brief that arrives in your inbox.

**Trigger:** Schedule — every Monday at 8am  
**Steps:**
1. Fetch data from your source (Google Sheets, a database, an API, recent emails)
2. Send to Claude: "Summarize the key highlights from this data. What are the top 3 things I should know?"
3. Format as a clean email
4. Send to yourself (or your team)

**Variations:**
- IT digest: pull ticket data from your helpdesk, summarize open vs closed, flag anything overdue
- Sales digest: pull CRM data, summarize pipeline, flag deals that haven't moved
- Project status: pull GitHub issues or project tasks, summarize what's done and what's blocked

**Build in:** n8n (best AI integration for this use case)

---

## 4. GitHub PR notification

**What it does:** When a pull request is opened in GitHub, post a notification to Slack with the PR title, author, and a link.

**Why it's useful:** Your team sees PRs immediately without checking GitHub. No more "I didn't know that was waiting for review."

**Trigger:** New GitHub pull request (opened)  
**Steps:**
1. Extract PR title, author, branch, and URL from the GitHub webhook
2. Post to Slack: `:git: New PR from {author}: *{title}*\n{url}`

**Optional AI step:** Add a Claude node to summarize what the PR does based on the PR description, then include that summary in the Slack message.

**Build in:** Any platform — GitHub integrations are universal. Zapier is simplest.

---

## 5. New contact onboarding

**What it does:** When a new contact is added to your CRM (or a Google Sheet), send them a welcome email and create a follow-up task for yourself.

**Why it's useful:** Automates the manual "remember to send the welcome email and set a reminder" workflow.

**Trigger:** New row in Google Sheet (or new contact in HubSpot, etc.)  
**Steps:**
1. Extract contact name, email, and how they found you
2. Optional: send to Claude to draft a personalized welcome email based on their context
3. Send the welcome email via Gmail
4. Create a follow-up task in your task manager (Todoist, ClickUp, Notion, etc.) — "Follow up with {name} in 3 days"

**Build in:** Make or n8n (both have good Google Sheets and Gmail integrations)

---

## Getting unstuck

**"I don't know how to call the Claude API from n8n/Make"**
Both have documentation on calling HTTP APIs. The Claude API endpoint is `https://api.anthropic.com/v1/messages`. The [n8n.md](./n8n.md) file has specific instructions.

**"My workflow is running but not doing what I expected"**
Every platform has a test/execution history view. Look at the data at each step — it shows you exactly what each node received and sent.

**"I keep hitting the free tier limit"**
Audit your workflows — most workflows can be made more efficient (e.g., filter before calling the AI, not after). Also consider whether n8n self-hosted is worth it for your use case (unlimited, free).

**"I want to build something not on this list"**
Post in the n8n community forum (community.n8n.io) — someone has probably built it already.
