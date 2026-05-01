# Make and Zapier

Make and Zapier are the two most widely used no-code automation platforms. Both are cloud-based, require no installation, and have large app libraries. They're good starting points if you want simpler setup than n8n.

---

## Make (formerly Integromat)

**Website:** https://make.com
**Free tier:** 1,000 operations/month, unlimited scenarios

**What it is:** A visual automation platform with a canvas-based editor. More powerful than Zapier's basic tier, with support for complex data transformation, loops, filters, and error handling.

**Strengths:**
- More flexible than Zapier for complex data manipulation
- Better free tier than Zapier (1,000 operations vs. 100 tasks)
- Excellent for transforming data between formats
- Good Claude/OpenAI integration via HTTP module or native AI modules
- Visual scenario editor is intuitive for beginners

**Limitations:**
- "Operations" billing model can get confusing — each step in a workflow uses operations
- Less extensive app library than Zapier
- Support can be slow on free tier

**Getting started:**
1. Sign up at https://make.com
2. Create a "Scenario" (Make's word for a workflow)
3. Choose a trigger module (Gmail, Schedule, Webhook, etc.)
4. Add action modules and connect them
5. Test and activate

**Connecting to Claude:**
Make has an "HTTP" module that lets you call any API. To call Claude:
1. Add an HTTP module
2. Set URL to `https://api.anthropic.com/v1/messages`
3. Add headers: `x-api-key: your-key`, `anthropic-version: 2023-06-01`
4. Set body to the Claude API format with your prompt

---

## Zapier

**Website:** https://zapier.com
**Free tier:** 100 tasks/month, 5 Zaps (workflows)

**What it is:** The original no-code automation platform. 6,000+ app integrations. Very simple "when this happens, do that" model.

**Strengths:**
- Largest app library — if a SaaS tool exists, Zapier probably has an integration
- Easiest onboarding — "Zaps" are simpler to build than n8n workflows or Make scenarios
- Reliable and well-documented
- Native Claude/AI integrations available

**Limitations:**
- Free tier is very limited (100 tasks/month, 5 Zaps)
- Paid tiers start at $20/month and get expensive
- Less flexible for complex data transformation
- Multi-step Zaps require a paid plan

**Getting started:**
1. Sign up at https://zapier.com
2. Click "Create Zap"
3. Choose a trigger app and event
4. Choose an action app and event
5. Connect your accounts and test
6. Turn on the Zap

**Connecting to Claude:**
Zapier has a native "Claude AI" integration. Search for it when adding an action step.

---

## Comparison table

| Feature | Make | Zapier | n8n |
|---|---|---|---|
| Free tier | 1,000 ops/month | 100 tasks/month | Self-host free; cloud free tier |
| App integrations | ~1,500 | ~6,000 | ~400 (growing) |
| Learning curve | Medium | Low | Medium-high |
| Data transformation | Excellent | Basic | Excellent |
| Self-host option | No | No | Yes |
| Claude integration | Via HTTP module | Native integration | Via credential node |
| Best for | Complex workflows on a budget | Simple connections, max integrations | Power users, AI-native workflows |

---

## Which to choose

**Choose Make if:**
- You need more than Zapier's free tier allows
- Your workflows involve complex data transformation
- You want more control than Zapier without going full n8n

**Choose Zapier if:**
- You need to connect an obscure SaaS tool (Zapier's library is biggest)
- You want the simplest possible setup
- You're doing simple one-trigger-one-action workflows
- Your company already has a Zapier account

**Choose n8n if:**
- You want maximum power and flexibility
- You're comfortable with a slightly steeper learning curve
- You want to self-host and control your data
- You're building AI-native workflows (n8n's AI nodes are better)

For this repo's audience, **n8n cloud** or **Make** are the recommended starting points.
