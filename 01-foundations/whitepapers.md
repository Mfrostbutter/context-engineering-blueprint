# Key AI Papers — Plain-English Summaries

You don't need to read these papers in full. The summaries below give you the key ideas. Links to the full papers are included if you want to go deeper.

---

## The transformer architecture

**Attention Is All You Need (Vaswani et al., 2017)**
https://arxiv.org/abs/1706.03762

**What it introduced:** The transformer — the architecture that powers every major AI model today (GPT, Claude, Gemini, Llama, etc.).

**Plain-English summary:** Before this paper, AI models for language were slow and struggled with long sequences. This paper introduced "attention" — a mechanism that lets the model focus on the most relevant parts of the input when generating each word, regardless of where those parts appear in the sequence. It was dramatically faster and more effective than what came before.

**Why it matters:** Every LLM you use today is built on this architecture. Understanding it gives you a mental model for why context windows exist and why some tasks are harder than others.

---

## The GPT-4 Technical Report (OpenAI, 2023)
https://arxiv.org/abs/2303.08774

**What it covers:** OpenAI's documentation of GPT-4's capabilities and safety evaluation.

**Plain-English summary:** GPT-4 scored in the top 10% on the bar exam, passed AP-level exams in most subjects, and outperformed GPT-3.5 significantly on reasoning tasks. The report also documents how they tested for unsafe behaviors and reduced them through fine-tuning.

**Why it matters:** A useful benchmark for what modern LLMs can and can't do. Also the first major "multimodal" model report — GPT-4 can process both text and images.

---

## Claude's Character (Anthropic, 2024)
https://www.anthropic.com/research/claudes-character

**What it covers:** How Anthropic developed Claude's values, curiosity, and identity through training.

**Plain-English summary:** Claude isn't just a language model that answers questions — Anthropic deliberately cultivated a consistent character: intellectual curiosity, warmth, directness, and a commitment to honesty. This paper explains how they did that through Constitutional AI and training processes.

**Why it matters:** Useful context for why Claude behaves differently from GPT models and why it pushes back on certain requests.

---

## Scaling Laws for Neural Language Models (Kaplan et al., 2020)
https://arxiv.org/abs/2001.08361

**What it introduced:** The relationship between model size, data, and compute — and how they predict performance.

**Plain-English summary:** More parameters + more data + more compute = better model, in a predictable mathematical way. This "scaling law" is why AI labs kept building bigger and bigger models through 2020-2023 and why it worked.

**Why it matters:** Explains the "bigger is better" era of AI and why it eventually hit diminishing returns, pushing toward techniques like RLHF, chain-of-thought, and better data curation instead.

---

## Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks (Lewis et al., 2020)
https://arxiv.org/abs/2005.11401

**What it introduced:** RAG — connecting language models to external knowledge bases.

**Plain-English summary:** Instead of memorizing all facts during training (which gets stale and has limits), train the model to first search a knowledge base for relevant information, then use that information to answer the question. This gives you a model that can work with up-to-date, private, or domain-specific information.

**Why it matters:** RAG is the foundation for most enterprise AI assistants, document Q&A systems, and anything that needs current or proprietary information. The "second brain" pattern in section 06 of this repo is a simple implementation of the same idea.

---

## Constitutional AI: Harmlessness from AI Feedback (Bai et al., 2022)
https://arxiv.org/abs/2212.08073

**What it introduced:** A technique for training AI to be helpful and harmless using AI-generated feedback.

**Plain-English summary:** Instead of relying entirely on human raters to label good vs. bad responses (expensive and slow), you give the model a set of principles ("the constitution") and have it evaluate its own outputs. The model learns to critique and revise its responses based on those principles. This scales better than pure human feedback.

**Why it matters:** This technique is behind Claude's safety training and explains why Claude is more consistent about refusing certain requests — it's internalized principles, not just memorized rules.

---

## Further reading

If you want to go deeper on any of these topics, the best resource is Andrej Karpathy's YouTube channel (see [youtube-channels.md](./youtube-channels.md)). He walks through the transformer architecture and LLM training in video form, building from scratch in code.
