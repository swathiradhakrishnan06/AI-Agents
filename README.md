# AI Agents
---

## 📑 Table of Contents

1. [What Are AI Agents?](#what-are-ai-agents)

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
