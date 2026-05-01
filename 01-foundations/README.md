# 01 — Foundations

Before you can use AI effectively, you need a working mental model of what it is and how it works. You don't need to understand the math — but you do need to understand the concepts.

This section covers:

- [Glossary](./glossary.md) — The terms you'll see everywhere, explained plainly
- [YouTube Channels](./youtube-channels.md) — The best channels for learning AI at every level
- [Whitepapers](./whitepapers.md) — The key research papers, with plain-English summaries

---

## The 5 concepts that matter most

### 1. Context window
The amount of text an AI can "see" at one time. Think of it as the AI's short-term memory. Everything you type in a conversation, plus the AI's responses, counts against this limit. Modern models have large context windows (100K–1M tokens), but it still fills up. This is why context engineering matters.

### 2. Tokens
The units AI models process. Not exactly words — a token is roughly 3/4 of a word in English. "context engineering" is 3 tokens. Why does this matter? Because API costs, context limits, and response speed are all measured in tokens.

### 3. Prompt
What you send to the AI. A prompt can be a question, an instruction, a document, or all three combined. The quality of your prompt directly determines the quality of the response.

### 4. LLM (Large Language Model)
The type of AI model behind tools like Claude, ChatGPT, and Gemini. These models were trained on massive amounts of text and learned to predict what comes next. That prediction ability turns out to be powerful enough to reason, write, code, and summarize.

### 5. RAG (Retrieval-Augmented Generation)
A technique where the AI looks up relevant information from a knowledge base before answering. Instead of relying only on what it was trained on, it retrieves current, specific information first. This is how enterprise AI assistants stay up-to-date and domain-specific.

---

## What to do next

1. Read the [glossary](./glossary.md) — bookmark it, you'll refer back to it
2. Watch one video from [the channels list](./youtube-channels.md) — the 3Blue1Brown transformer video is the best starting point
3. Skim one [whitepaper summary](./whitepapers.md) — read the plain-English version, not the full paper

Then move to [02 — GitHub Basics](../02-github-basics/).
