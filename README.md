# AI Agents
---

## 📑 Table of Contents

1. [What Are AI Agents?](#1-what-are-ai-agents)
2. [Inside the Brain of AI Agents: Large Language Models](#2-inside-the-brain-of-ai-agents)

---
## 1: What Are AI Agents?

### 🔥 Why AI Agents Matter

* **Market Signals:**

  * **Job Growth:** Strong market projections for AI agents (2023–2033).
  * **Funding:** Surge in investor interest.
* **Foundational Research (2023 Highlights):**

  * *Chain of Thought Prompting* – Reasoning capabilities in LLMs.
  * *ReAct* – Merging reasoning and action in LLMs.
  * *ToolFormer* – Equipping LLMs to use tools.
  * *Generative Agents* – Human-like behavioral simulation.

These research papers form the backbone of modern agent applications and frameworks.

---

### 🧩 Defining an AI Agent (First Principles Approach)

1. **Initial Insight:** Helps user go from *Point A → Point B* (e.g., planning a trip).
2. **Added Capabilities:** Can **plan** and **make decisions**.
3. **Crucial Element:** Uses **tools** (e.g., web search, booking systems).
4. **Further Requirements:**

   * **Memory:** Learns from past interactions.
   * **Human Feedback:** Adapts through evaluation.
   * **Environmental Interaction:** Acts in the external world.

> 📌 **Formal Definition:**
> An AI agent is a system that:
>
> * Takes you from point A to point B and adds value (saves time/money),
> * Has access to tools to make decisions and plan,
> * Interacts with the external environment,
> * Possesses memory to learn from past actions,
> * Incorporates human feedback for improvement.

---

### 🧠 Role of Large Language Models (LLMs)

* **Key Enabler:** Agents became viable after the **Transformer architecture** (*Attention is All You Need*, 2017).
* **Language as the Core:**
  Language enables agents to plan, make decisions, and interact with external systems.
* **LLMs = Brain of the Agent:**
  The LLM handles reasoning and planning, while tools serve as the agent’s **body** to perform actions.

> ⚠️ *Important Distinction:*
> LLMs alone ≠ agents.
> They don't act independently, plan, or interact with the real world unless paired with tools.

---

### 🎛️ Levels of Agency

| Level                   | Description                              | Example                                        |
| ----------------------- | ---------------------------------------- | ---------------------------------------------- |
| **Low Agency**          | Minimal decision-making; just uses tools | ChatGPT with a web search plugin               |
| **High Agency**         | Plans, decides, executes actions         | Travel planner, sales automation agent         |
| **Multi-Agent Systems** | Multiple agents coordinate tasks         | Travel planner calling a booking + email agent |

> 💡 **Higher agency = Higher value creation**
> Value is measured by saved time, cost reduction, or increased revenue.

---

### 🧪 Case Study: Automated Video Interview Analysis

* **Use Case:** Analyze 500+ video job applications.
* **Agent Tasks:**

  * Visit hiring platform and download videos.
  * Convert video → transcript (speech-to-text).
  * Analyze sentiment using LLM.
  * Rank candidates based on analysis.
* **Agentic Features:**

  * **Decision-making:** Candidate ranking.
  * **Tool use:** Scraping, downloading, converting, analyzing.
  * **Feedback Loop:** Manager reviews samples and updates agent behavior (learning).
  * **High Agency:** Interacts with environment, applies feedback, executes multi-step processes.

---
## 2. Inside the Brain of AI Agents: Large Language Models

This section explains the foundational role of **Large Language Models (LLMs)** in powering AI agents — acting as their "brain" — and covers the principles behind their design, training, and capabilities.

### 🧠 1. LLMs as the Core of AI Agents

* LLMs are essential to the function of AI agents: they enable planning, decision-making, and interaction with external tools and environments.
* Without LLMs, agents cannot operate in their current form. Understanding LLMs is critical to building or reasoning about agents.
* AI agents:

  * Take users from point A to B while adding value.
  * Can plan and take decisions.
  * Have access to tools (e.g., Google Search, email, booking portals).
  * Interact with external environments.
  * Possess memory.

### 🔤 2. What Are LLMs? Next Token Prediction

* At their core, LLMs perform **next token prediction**.
* Given a sequence of words, the LLM **predicts the most likely next word/token**.
* This is **probabilistic**, not deterministic — multiple options are evaluated with probabilities.
* Analogy: Like a super-intelligent alien trying to complete the sentence "your effort will take you..." based on massive textual knowledge.
* A naive statistical method (e.g., brute force) is impractical due to exponential possibilities — hence, a **model** is required to generalize patterns.

### 📏 3. The "Large" in LLMs

* The "large" refers to **billions of parameters**.

  * Linear model: 2 parameters
  * Quadratic: 3 parameters
  * LLMs: **Billions**
* These parameters are adjusted during training to best predict the next token.

### ✨ 4. Why So Many Parameters?

Two main reasons:

1. **Emergent Properties**:

   * New abilities appear only in larger models beyond a certain size.
   * Examples: arithmetic, translation, word unscrambling.
   * These capabilities are **not present** in smaller models.

2. **Learning Language**:

   * To predict the next token, the model must implicitly **learn the language itself**.
   * It learns:

     * **Form**: Grammar, sentence structure (e.g., Subject-Verb-Object).
     * **Meaning**: Contextual understanding of phrases and facts (e.g., “blue electrons eat fish” is grammatically valid but meaningless).

### 🚀 5. Evolution of LLMs

* **Transformer architecture (2017)** was the breakthrough.
* Major model milestones:

  * **GPT-2 (2018)**: 1.5B parameters, introduced unsupervised multitask learning.
  * **GPT-3 (2020)**: 175B parameters, showed size improves accuracy significantly.
  * **GPT-3.5 (2022)**: Base of ChatGPT, more commercially usable.
  * **GPT-4 (current)**: Estimated to exceed 1T parameters, with better reasoning.
* Growth has been **exponential**, from 1M (2000) → 1T (2020).

### 🏗️ 6. How LLMs Are Built

LLMs are built in three phases:

1. **Data Aggregation**:

   * Collecting massive datasets from the internet (e.g., Common Crawl, OpenWebText).
   * Data scale: **trillions of words**.

2. **Pre-Training**:

   * Using the transformer architecture to train the model to predict next tokens.
   * Very expensive (e.g., **\$4.6M** to pre-train GPT-3).
   * Output: a **foundational model**, not yet specialized.

3. **Fine-Tuning**:

   * Uses **labelled data** to teach specific tasks (e.g., summarization, translation).
   * Converts a raw model into a product like ChatGPT.

### 🔄 7. LLMs vs Traditional NLP

* Traditional NLP required **separate models for each task** (e.g., grammar check, sentiment analysis).
* LLMs can perform **all these tasks using a single model** trained to predict the next token — often even **without fine-tuning**.

### 🧩 8. Position in the AI Hierarchy

```
Artificial Intelligence (AI)
└── Machine Learning (ML)
    └── Deep Learning
        └── Generative AI
            └── Language Models (LLMs)
```

* LLMs are the **most specific subset**, focused solely on language-based generation and understanding.

### ⚙️ 9. Small Language Models (SLMs)

* SLMs (10M–50M parameters) are gaining traction for **enterprise-specific** use cases.
* Can be trained on **company-specific data** ("corporate brain").
* Offer cost-effective, tailored performance without needing massive infrastructure.

---
