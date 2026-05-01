# AI Glossary

Plain-English definitions for the terms you'll encounter most often.

---

**Agent**
An AI that can take actions — not just respond to questions. An agent can read files, run code, search the web, and call external services. Claude Code is an agent. A plain chat window is not.

**Context window**
The total amount of text an AI model can process at once — including everything you've typed, everything it's responded, and any files or documents you've attached. When the context window fills up, the model starts "forgetting" earlier parts of the conversation.

**Context engineering**
The practice of structuring your files, instructions, and knowledge so an AI always has the right information available — without you having to re-explain it every session. This repo is about context engineering.

**Embedding**
A way of representing text as a list of numbers (a vector) so that similar ideas end up close together mathematically. Embeddings are what power semantic search — finding documents that mean the same thing, even if they use different words.

**Fine-tuning**
Training a pre-built model on additional data to specialize it for a specific task or style. Expensive and usually unnecessary — prompt engineering and context engineering can solve most of the same problems for free.

**Grounding**
Connecting an AI's response to real, verifiable information — usually through RAG or by giving it documents to read. "Grounded" responses are anchored to actual sources. "Ungrounded" responses are the AI reasoning from memory, which can produce hallucinations.

**Hallucination**
When an AI confidently states something that is false. This happens because LLMs are prediction engines, not fact databases — they predict plausible-sounding text, which is sometimes wrong. Grounding and verification reduce (but don't eliminate) this.

**Inference**
The act of running an AI model to generate a response. When you send a message to Claude and it responds, that's an inference. Inference costs money (API calls) and takes time (latency).

**LLM (Large Language Model)**
The type of AI model that powers Claude, ChatGPT, Gemini, and most modern AI assistants. Trained on massive text datasets to predict what comes next in a sequence of text. The "large" refers to the number of parameters — the internal values learned during training.

**MCP (Model Context Protocol)**
An open standard for connecting AI models to external tools and data sources. An MCP server exposes a set of tools (functions) that an AI agent like Claude Code can call. Think of it as a plugin system for AI.

**Parameters**
The internal numeric values of an AI model, adjusted during training. A model with "70 billion parameters" has 70 billion of these values. More parameters generally means more capability — and more cost to run.

**Prompt**
The input you give to an AI. Can be a question, a command, a document, or a combination. The structure and content of your prompt heavily influence the quality of the response.

**Prompt engineering**
The skill of crafting prompts that consistently produce useful outputs. Important, but limited — prompt engineering works within a single conversation. Context engineering works across sessions.

**RAG (Retrieval-Augmented Generation)**
A technique where the AI retrieves relevant documents from a knowledge base before generating a response. The retrieved documents are injected into the context window, giving the AI current, specific information to work from.

**System prompt**
A special prompt that sets the AI's behavior and context before the conversation starts. In Claude Code, the `CLAUDE.md` file acts like a persistent system prompt — the AI reads it at the start of every session.

**Temperature**
A setting that controls how "creative" or "random" the AI's responses are. Low temperature = more predictable, focused responses. High temperature = more varied, creative responses. Most coding and analysis tasks use low temperature.

**Token**
The unit AI models process text in. Roughly 3/4 of an English word. "context engineering" = 3 tokens. Token counts determine API cost, context limit usage, and response speed.

**Vector database**
A database designed to store and search embeddings. Used in RAG systems to find relevant documents quickly. Examples: Qdrant, Pinecone, Weaviate, Chroma. For beginners, a folder of markdown files often works just as well.
