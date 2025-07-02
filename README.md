# AI Agents
---

## 📑 Table of Contents

1. [What Are AI Agents?](#1-what-are-ai-agents)
2. [Inside the Brain of AI Agents: Large Language Models](#2-inside-the-brain-of-ai-agents-large-language-models)
3. [Understanding AI Agents and the ReAct Framework](#-3-understanding-ai-agents-and-the-react-framework)
4. [AI Agentic Frameworks: A Comprehensive Briefing](#-4-ai-agentic-frameworks-a-comprehensive-briefing)
5. [Smolagents, Code Agents, Tool-Calling Agents, and Langfuse](#5--smolagents-code-agents-tool-calling-agents-and-langfuse)


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

## 🎯 3. Understanding AI Agents and the ReAct Framework

This section introduces the foundational concepts behind AI agents, how they extend the capabilities of LLMs, and the role of the ReAct (Reasoning and Action) framework in enabling intelligent, tool-using behaviour.

---

### 🧠 Core Concept of AI Agents

* **Definition**: AI agents are enhanced LLMs that can **plan, decide, act, and interact** with their environment to provide real-world utility.
* **Foundation**:

  > “The foundation of agents is something which is called as a large language model.”
  > LLMs act as the **brain** of agents, taking word sequences as input and predicting the next token while learning both form and meaning.
* **Emergent Properties**:
  LLMs gain **emergent capabilities** once they reach a certain scale, which makes them suitable for reasoning and planning tasks.
* **Augmentation**:
  Agents are formed by **augmenting LLMs** with the ability to:

  * Plan and take decisions
  * Use external tools
  * Interact with an environment
  * Remember past interactions

---

### 🛠️ Role and Integration of Tools

* **Definition**:

  > “Tools are weapons which a large language model receives so that it can interact with its environment.”
  > Tools extend the LLM’s ability to **act beyond language**.
* **Examples**:

  * 🔍 Web Search: DuckDuckGo, SerpAPI
  * ➕ Math: LLM Math tool
  * 🎨 Code/Image: Generation or evaluation tools
  * 🌦️ APIs: GitHub, YouTube, Spotify, Weather APIs
* **Tool Usage via Prompts**:

  * Tools are **defined and described in the prompt**
  * The LLM **calls a tool** by writing a specific string (tool call)
  * Agent **executes the call** and observes the result
  * > “Prompt engineering is extremely important because it’s how you convey in the prompt that… here are the tools which you have to use.”
* **Complementing LLM Weaknesses**:

  * Struggles with math? ➡️ Use a calculator tool
  * Needs real-time data? ➡️ Use a search tool
* **Custom Tools**:

  * You can create tools with **simple custom functions** and define them in the prompt.

---

### 🔁 The ReAct Framework: Reasoning + Action

* **Background**:

  * Based on **Chain-of-Thought (CoT)** prompting:

    > “Generate reasoning traces or thoughts” through examples in the prompt
    > Helps the LLM simulate **thinking** and **planning**
  * Limitation: CoT **cannot act**—it’s only internal reasoning.
* **The ReAct Loop (TAO)**:
  Adds **acting + observation** through a structured loop:

  1. **Thought** – Internal reasoning (“what should I do?”)
  2. **Action** – Executes the next step (often via tools)
  3. **Observation** – Feedback from tool or environment
* **Key Principle**:

  > “This thought–action–observation framework is repeated n times... until the LLM thinks it has the right answer.”
* **Memory**:

  * The loop depends on remembering past interactions to guide future actions.
* **Implementation**:

  * The ReAct loop is **implemented entirely in the prompt**

---

### 🧰 Building an AI Agent: LLM + Tools + Prompt

* **Essential Components**:

  * 🧠 **LLM**: E.g., GPT-3.5 Turbo
  * 🔧 **Tools**: DuckDuckGo search, LLM Math, APIs
  * ✍️ **Prompt**: Encodes how to think, reason, and use tools
* **Frameworks**:

  * **LangChain** helps structure agents:

    * Predefined tools
    * Prompt templates (`create_react_agent`)
    * Agent lifecycle management
  * > “LangChain is the main framework in which we are going to develop our first agent today.”
* **Execution**:

  * The agent **calls the LLM** with prompt + tools
  * Enables reasoning, planning, and real-world interaction
* **Limitations & Guardrails**:

  * ❗ **Hallucinations** – Agents can still generate false or misleading info
  * 🔁 **Endless Loops** – Prevent with `max_iterations`
  * 🔒 **Guardrails** – Evaluation layers to ensure output quality and safety

---

### 🍬 Analogy: Kid Searching for Candy (TAO in Action)

* A child must find a chair with candy among five:

  1. 🧠 Thinks: “Let me check the first chair”
  2. 🏃 Acts: Moves to the chair
  3. 👀 Observes: No candy found

  * Repeats the process until successful
* Mirrors an agent’s **Thought–Action–Observation** cycle, using memory and feedback to guide exploration

---

### ✅ Summary

> “Agents are glorified language models who have access to tools, who have access to environment, who can reason and plan with memory.”

The **ReAct framework**, paired with **strategic prompt engineering** and **tool integration**, transforms a static LLM into an intelligent agent capable of decision-making, interaction, and iterative reasoning.

---

## 🧱 4. AI Agentic Frameworks: A Comprehensive Briefing

This briefing explores a spectrum of AI agentic frameworks, grouped into **code-based**, **low-code**, and **no-code** solutions. It covers foundational concepts, key tools, and real-world applications using the ReAct-based agent model.

---

### 🧠 1. Understanding AI Agents and Their Foundations

* **Definition**:

  > "An agent is just a language model which has access to tools through the prompt."
  > Agents take **text input** and return **text output**, augmented with tool-use capabilities and governed by prompt instructions.

* **Key Concepts**:

  * **Tools**:

    > "Weapons which an LLM receives to perform a certain action."
    > Defined in the system prompt, tools enable tasks like:

    * 🧮 Calculator: Performs arithmetic.
    * 🌐 URL Tool: Reads and understands web content.
  * **Prompt Engineering**:

    > "An extremely important ingredient for agents."
    > Crafting detailed prompts defines the tools and agent behavior.
    > "The more details you write the better you extract from the language model."
  * **Chain of Thought vs ReAct**:

    * **Chain of Thought (CoT)**: Produces reasoning traces but

      > "Don't interact with the external environment and hence they cannot take actions."
    * **ReAct Framework**:

      > "Goes a step further by introducing the thought action observation loop."
      > This **TAO loop** is
      > "The heartbeat of the react agent"
      > allowing memory, planning, and real-world interaction. Agents with this loop have a higher "level of agency."

---

### 🧰 2. The Rise of Agentic Frameworks

Agentic frameworks offer various degrees of control and accessibility for building intelligent agents, depending on coding proficiency.

---

#### 💻 Code-Based Agentic Workflows

* **Audience**: Developers, enterprise teams, students who prefer full control.
* **Advantages**: Maximum flexibility, full system integration.
* **Popular Frameworks**:

  * **LangGraph**:

    > "By far the most popular codebased agentic workflow at the moment."
    > Considered superior to LangChain and supports `create_react_agent`.
  * **LangChain**:

    > "Still popular... though LangGraph is now recommended."
  * **LlamaIndex**:

    > "Good for RAG-based applications... now supports agentic workflows."
  * **Small Agents (Hugging Face)**:

    > "Simplest codebased framework to learn"
    > and described as "a very simple library."
  * **AutoGen (Microsoft)**: Another popular code-based framework.
* **Implementation**: Typically done in environments like Google Colab.

---

#### 🧩 Low-Code Agentic Workflows

* **Audience**: Users with limited or no coding background.
* **Advantages**: Visual workflows, drag-and-drop features with optional code access.
* **Popular Frameworks**:

  * **Langflow**:

    > "Drag and drop tools" + access to underlying code.
    > Includes templates like a **travel planning agent** (multi-agent system).
  * **CrewAI**:

    > "Extremely good for organizing multiple agents together."
    > Code reads almost like natural language.
  * **N8N**:

    > "Add custom code as well"
    > via visual, platform-agnostic interface.
  * **Make.com**:

    > "Almost fully no code" but included under low-code.
  * **Agnos**:

    > "Fully open source" and supports full-stack multi-agent systems. Less popular but notable.

---

#### ⚙️ No-Code Agentic Workflows

* **Audience**: Non-coders seeking automation with full abstraction.
* **Advantages**: Fully visual, no technical input required.
* **Popular Platforms**:

  * **Microsoft Copilot Studio**
  * **Google Vertex AI / AI Studio**:
    Vertex AI offers no-code features; AI Studio includes Agent Development Kit (ADK).
  * **Manus**:

    > "Absolutely incredible no code platform"
    > that orchestrates multiple agents with transparency via a visible side panel.
  * **OpenAI Deep Research** (ChatGPT):

    > "Multiple agents work together... fully no code."
  * **Claude and Gemini Deep Research**:
    Similar no-code capabilities from other providers.

---

### 🚀 3. Practical Applications and Demonstrations

Examples demonstrate how various frameworks enable real-world agentic tasks.

---

#### 🧪 Langflow Demonstrations

Langflow is showcased as an intuitive, visual platform that supports both single and multi-agent systems. It allows for easy tool integration and agent chaining via a graphical interface.

* **Simple Agent**:

  * A basic Langflow setup with **two tools**:

    * 🔗 **URL Tool**: Enables the agent to fetch and understand the contents of any provided webpage.
    * 🧮 **Calculator Tool**: Lets the agent perform arithmetic operations.
  * **Demonstration**:
    A user inputs a query like “What is on this website and what’s 132 + 48?” The agent:

    1. Analyzes the query.
    2. Uses the **URL Tool** to fetch the webpage content.
    3. Applies the **Calculator Tool** to answer the math portion.
    4. Returns both outputs in a coherent response.
  * **Takeaway**: This illustrates how agents can **select tools autonomously** based on task understanding, with Langflow managing tool registration and agent logic through its UI.

* **Travel Itinerary Agent (Multi-Agent System)**:

  * This complex setup involves **three agents**, each responsible for part of the itinerary pipeline:

    1. **City Selection Agent**: Uses a **Search API Tool** to find travel destinations matching user preferences (e.g., warm beach cities in July).
    2. **Local Expert Agent**: For the selected city, it retrieves detailed content from travel blogs using:

       * The same **Search API**
       * A tool to **scrape and retrieve structured data from URLs**
    3. **Travel Concierge Agent**: Aggregates data from the previous agents and builds:

       * A daily travel plan
       * Estimated budget using the **Calculator Tool**
  * **Demonstration Flow**:

    * The user provides a high-level travel requirement.
    * The agents **sequentially hand over results**:

      * City selection → deep guide gathering → itinerary generation.
  * **Takeaway**:
    Demonstrates **accountable agents** that work independently and collaboratively.

    > "Every agent is accountable, every agent does its own thinking and then the next agent is called."
    > This modularity boosts system transparency and debugging ease.

* **YouTube Analysis Workflow**:

  * Tools used:

    * 🎥 **YouTube Transcript Tool**: Pulls and parses spoken content from videos.
    * 💬 **YouTube Comments Tool**: Collects and summarizes public sentiment.
  * **Demonstration**:

    * The user enters a video link.
    * The agent uses both tools to provide:

      * A high-level video summary.
      * Sentiment analysis and key trends from viewer comments.
  * **Takeaway**:
    A compelling use case for content analysis, enabling **market research, influencer tracking, or feedback mining** from video platforms.

---

#### 🛠️ N8N Demonstration

N8N's block-based, visual interface is highlighted as a flexible way to build agents with **tool access and memory integration**, particularly for users who want **some coding control but in a low-code environment**.

* **Demonstration Scenario**: Predicting **Nvidia stock price**.

  * The agent is built by chaining multiple blocks:

    1. **Input Node**: Accepts a user query like “What is Nvidia’s future stock trend?”
    2. **SERP API Tool Node**: Performs a web search to gather recent predictions and news.
    3. **Memory Node**: Stores retrieved information for potential reuse in follow-up queries.
    4. **Response Node**: Synthesizes results and returns an answer.
  * **Interactive Features**:

    * Users can **visually inspect each node’s configuration**, logic, and data flow.
    * Option to add **custom JS code** inside nodes for added control.
  * **Takeaway**:
    N8N offers a **hybrid experience**—users can build visually but also tweak behavior through embedded scripting. It’s ideal for quickly testing agents that combine API calls, data processing, and output formatting.

---

#### 📄 Manus Demonstration

Manus is portrayed as an **enterprise-grade, no-code** platform that can orchestrate multiple agents to **perform full research workflows**. It provides a side-by-side interface showing both inputs and agent decisions.

* **Demonstration Scenario**: Compare **PostgreSQL vs. MongoDB** for an internal tech decision or client recommendation.

  * **Agents Used**:

    1. **File Agent**: Collects and stores intermediate results or external files.
    2. **Searching Agent**: Uses a web search API to gather articles, benchmarks, and blog posts.
    3. **Editing Agent**: Cleans, extracts relevant data, and prepares summaries.
    4. **Writing Agent**: Generates a structured report including pros/cons, use cases, and recommendations.
  * **Workflow**:

    * Each agent operates with autonomy and clarity, executing tasks in a defined sequence.
    * The **side panel shows real-time agent interactions**, enabling the user to see:

      * Which agent was triggered
      * What it found or wrote
      * The rationale behind transitions
  * **Output**: A clean, detailed document tailored for business or technical decisions.
  * **Takeaway**:
    Manus excels at automating **multi-step knowledge workflows** without writing a single line of code. It’s especially useful in environments like consulting, research, and documentation-heavy industries.

---

### 🔮 4. Future Outlook and Recommendations

* **Code-Based**:

  * Ideal for deep integration in enterprise
  * Recommended tools: **LangGraph**, **LlamaIndex**, **Small Agents**

* **Low-Code**:

  * Suited for fast prototyping and ease of use
  * **N8N**, **CrewAI**, **Langflow** especially noted

* **No-Code**:

  * Best for non-technical users needing powerful automation
  * **Manus** and **OpenAI Deep Research** offer rich features

* **Emerging Trends**:

  * Growth in **multi-agent systems**
  * Rise of **browser agents** capable of autonomous web navigation
  * Importance of **evaluation frameworks** like:

    * 🧪 **Langfuse**
    * 📊 **Arise**

* **What’s Ahead**:

  * Hands-on coding with **Small Agents** to build:

    * Single agents
    * Multi-agents
    * Browser agents
    * Vision agents
  * Focus on **agent performance enhancement**

---

## 5. 🧠 Smolagents, Code Agents, Tool-Calling Agents, and Langfuse

This section explores the foundational concepts of **Smolagents**, a lightweight agentic framework, and the distinctions between **code agents** and **tool-calling agents**. It also explains how **Langfuse** provides observability and evaluation for agent workflows.

---

### 1. 🔹 Introduction to AI Agents and Smolagents

AI agents are defined as systems that:

* Can **plan and make decisions**
* Have **access to tools**
* Are powered by a **language model (LLM)**
* Can **interact with the environment**
* Possess **memory**

**Smolagents** is an open-source Python framework designed to make it easy to build and run agents with minimal code.

> “Build and run agents using just a few lines of code.”

#### 🧭 Thought-Action-Observation (TAO) Loop

This is the core iterative loop followed by AI agents:

1. **Thought** – The agent reasons about the task.
2. **Action** – Executes a tool or a code block.
3. **Observation** – Receives feedback and updates memory.

This loop repeats until a `final_answer` is produced. This sets agents apart from plain LLMs:

> “LLM is just one small aspect of this entire loop — that whole loop is an agent.”

---

### 2. ⚙️ Code Agents vs. Tool-Calling Agents

These two agent types differ in how they take actions.

---

#### 🛠️ Tool-Calling Agents

* Use **structured text or JSON** to call tools.
* Tools are passed explicitly in a standardized format.

**Example**: To find the cheapest smartphone worldwide:

* A tool-calling agent would perform individual tool calls for each country using structured instructions.

**Advantages**:

* Structured and predictable
* Well-suited for simple, repetitive tasks

**Disadvantages**:

* Less flexible
* Multiple repetitive actions for what could be a single, consolidated process

---

#### 💻 Code Agents

* Generate and execute **code blocks** (usually Python).
* The LLM itself generates the code during the TAO loop.

**Example**: To find the cheapest smartphone:

* A code agent generates a Python script that:

  1. Iterates over multiple countries
  2. Fetches prices
  3. Converts currencies
  4. Finds the minimum

**Advantages**:

* High flexibility and control
* Allows integration with any Python library
* Executes complex logic in fewer steps
* Recommended for complex production workflows

**Disadvantages**:

* More complex to manage
* Risk of runtime errors
* Security implications if code is leaked

> “You can literally plug and play any different Python packages into this code.”

---

### 3. 🧠 Agent Memory and Optimisation

Agent memory stores previous thoughts, actions, and observations.

* Memory is appended to the agent’s prompt to provide **contextual awareness**.
* This is crucial for long multi-step tasks.

Two strategies for memory optimization:

1. **Conversation Window Buffer**

   * Limits how much past context is retained.
2. **Summarisation**

   * Summarizes history to reduce memory size but can cause minor loss in accuracy.

> “The LLM can make a summary of your history — similar to how humans do.”

---

### 4. 🔍 Agent Evaluation and Observability with Langfuse

Directly viewing agent output in the console has limitations:

* Poor formatting
* Difficult to debug
* “Black box” execution

**Langfuse** solves this by offering detailed, structured observability.

#### ✅ Key Features

* **Trace Inspection**: See every step in the TAO loop — thoughts, actions, tool calls, and observations.
* **System Prompt Disclosure**: Shows the hidden prompt used internally, including few-shot examples and code execution logic.
* **Performance Metrics**:

  * Input/output tokens
  * Total LLM calls
  * Response times
* **Error Tracking**: Identifies where the agent fails.
* **LLM Evaluators**: Supports evaluation based on metrics like hallucination, relevance, faithfulness, and context recall.

> “Langfuse opens the black box... you can see how the code works, what tools were called, and what happened.”

---

### 🧪 Code Setup

#### Installation and Authentication

```python
!pip install smolagents -U
!pip install duckduckgo-search

from huggingface_hub import notebook_login
notebook_login()
```

#### Langfuse Telemetry Integration

```python
!pip install smolagents[telemetry] opentelemetry-sdk opentelemetry-exporter-otlp openinference-instrumentation-smolagents

import base64
import os

os.environ["LANGFUSE_PUBLIC_KEY"] = ""
os.environ["LANGFUSE_SECRET_KEY"] = ""

LANGFUSE_PUBLIC_KEY = os.environ.get("LANGFUSE_PUBLIC_KEY")
LANGFUSE_SECRET_KEY = os.environ.get("LANGFUSE_SECRET_KEY")

if not LANGFUSE_PUBLIC_KEY or not LANGFUSE_SECRET_KEY:
    raise ValueError("Langfuse public or secret keys are missing!")

LANGFUSE_AUTH = base64.b64encode(f"{LANGFUSE_PUBLIC_KEY}:{LANGFUSE_SECRET_KEY}".encode()).decode()

# Uncomment the appropriate region
# os.environ["OTEL_EXPORTER_OTLP_ENDPOINT"] = "https://cloud.langfuse.com/api/public/otel" # EU
os.environ["OTEL_EXPORTER_OTLP_ENDPOINT"] = "https://us.cloud.langfuse.com/api/public/otel" # US
os.environ["OTEL_EXPORTER_OTLP_HEADERS"] = f"Authorization=Basic {LANGFUSE_AUTH}"

print("Langfuse environment variables set successfully!")
```

#### Langfuse Tracer Setup

```python
from opentelemetry.sdk.trace import TracerProvider
from openinference.instrumentation.smolagents import SmolagentsInstrumentor
from opentelemetry.exporter.otlp.proto.http.trace_exporter import OTLPSpanExporter
from opentelemetry.sdk.trace.export import SimpleSpanProcessor

trace_provider = TracerProvider()
trace_provider.add_span_processor(SimpleSpanProcessor(OTLPSpanExporter()))
SmolagentsInstrumentor().instrument(tracer_provider=trace_provider)
```

---

### 5. 🧪 Practical Examples

#### 🔍 Web Search Agent

A web search agent is built to provide AI/ML book recommendations using the **DuckDuckGo search tool**. It is demonstrated using both agent types.

```python
from smolagents import CodeAgent, ToolCallingAgent, InferenceClientModel
from smolagents.tools import DuckDuckGoSearchTool

# Code Agent
agent = CodeAgent(
    tools=[DuckDuckGoSearchTool()],
    model=InferenceClientModel(provider="together")
)
agent.run("Search for the best book recommendations for implementing AI in the workplace.")

# Tool-Calling Agent
agent = ToolCallingAgent(
    tools=[DuckDuckGoSearchTool()],
    model=InferenceClientModel(provider="together")
)
agent.run("Search for the best book recommendations for implementing AI in the workplace.")
```

---

#### 🖼️ Vision Agent

This example uses a multimodal LLM to analyze image inputs and identify comic characters.

* Two images of the **Joker** are fetched from the web.
* The model is asked to describe the character’s costume and makeup and identify whether it's **The Joker** or **Wonder Woman**.
* No additional tools are required.

```python
from PIL import Image
import requests
from io import BytesIO

image_urls = [
    "https://upload.wikimedia.org/wikipedia/commons/e/e8/The_Joker_at_Wax_Museum_Plus.jpg",
    "https://upload.wikimedia.org/wikipedia/en/9/98/Joker_%28DC_Comics_character%29.jpg"
]

images = []
for url in image_urls:
    headers = {
        "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/114.0.0.0 Safari/537.36"
    }
    response = requests.get(url, headers=headers)
    image = Image.open(BytesIO(response.content)).convert("RGB")
    images.append(image)

from google.colab import userdata
import os
os.environ["OPENAI_API_KEY"] = ""

from smolagents import CodeAgent, OpenAIServerModel

model = OpenAIServerModel(model_id="gpt-4o")

# Instantiate the agent
agent = CodeAgent(
    tools=[],
    model=model,
    max_steps=20,
    verbosity_level=2
)

response = agent.run(
    """
    Describe the costume and makeup that the comic character in these photos is wearing and return the description.
    Tell me if the guest is The Joker or Wonder Woman.
    """,
    images=images
)
```

> “The agent needs no tools because just the multimodal language model itself is enough.”

---

### 6. 🔮 Upcoming Topics

Future lessons will cover:

* **Multi-Agent Systems**:

  * Agents collaborating by passing off responsibility
* **Browser Agents**:

  * Automating browser-based interactions
* **Advanced Frameworks**:

  * LangGraph
  * LlamaIndex
  * Agentic RAG
  * CrewAI

---

