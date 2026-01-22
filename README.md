# SIG-AI-SDLC

Special Interest Group tracking AI Software Development LifeCycle tools and methodologies. 
aka Agentic AI Software Factory.

## Definition 

Define 'AI software factory' or 'AI SDLC' or 'Agentic SDLC' or 'Agentic Software Factory'

In the technology landscape of 2026, the terms you’ve listed represent the evolution of software engineering from a human-centric craft to an industrialized, AI-orchestrated process. While they are often used interchangeably, they represent distinct layers of the "intelligence-first" development era.

---

### 1. AI Software Factory

An **AI Software Factory** is the **infrastructure and operational model** designed to produce software at an industrial scale using AI.

* **Definition:** A centralized, highly standardized environment that treats software development like a manufacturing line. It integrates data pipelines, compute resources (like NVIDIA’s AI Enterprise or HPE’s specialized clusters), and automated governance into a single "production floor."
* **Key Focus:** Industrialization, predictability, and scalability. In 2026, this is the "hardware and backbone" layer that allows enterprises to run thousands of AI-assisted development projects simultaneously without fragmentation.

### 2. AI SDLC (AI-Enhanced Software Development Life Cycle)

The **AI SDLC** is the **methodology** of applying AI tools to traditional software development phases.

* **Definition:** An evolution of the classic Waterfall or Agile SDLC where every stage—Planning, Analysis, Design, Implementation, Testing, and Maintenance—is augmented by AI.
* **How it works:** Instead of humans writing every line, they use "Copilots" to generate boilerplate, "AI-Explainers" to document legacy code, and "Predictive Analytics" to estimate sprint velocity.
* **Evolution:** In 2026, we have moved from "AI-assisted" (human does the work, AI helps) to "AI-native" (AI does the bulk, human reviews).

---

### 3. Agentic SDLC

The **Agentic SDLC** represents a paradigm shift where **autonomous agents**, rather than static tools, take ownership of specific outcomes.

* **Definition:** A development process where the human "articulates intent" (e.g., "Build a subscription billing module") and a network of AI agents plans and executes the necessary steps across the lifecycle.
* **Key Differentiator:** While the AI SDLC uses AI as a *tool* (reactive), the Agentic SDLC uses AI as a *teammate* (proactive). These agents can make decisions, use tools (via the Model Context Protocol or MCP), and handle multi-step reasoning without constant human prompting.

### 4. Agentic Software Factory

The **Agentic Software Factory** is the **mature implementation** of the Agentic SDLC within an industrial framework.

* **Definition:** A "lights-off" or semi-autonomous development environment where specialized AI agents (Architects, Coders, Security, and QA) are orchestrated by a "Manager Agent" to deliver end-to-end software products.
* **Architecture:** It typically uses a multi-agent orchestration framework (like LangGraph, CrewAI, or Microsoft’s unified Agent Framework) to coordinate specialized agents that "talk" to each other to resolve bugs, optimize performance, and deploy code.

---

### Key Comparisons at a Glance

| Concept | Primary Driver | Human Role | Output |
| --- | --- | --- | --- |
| **Traditional SDLC** | Human Developers | Creator & Orchestrator | Hand-written Code |
| **AI SDLC** | AI Tools + Humans | Creator (AI-assisted) | AI-Generated Code |
| **Agentic SDLC** | Autonomous Agents | Intent-Setter / Reviewer | Validated Solutions |
| **Agentic Software Factory** | Orchestrated Agent Crews | Governance / "Reviewer-in-Chief" | End-to-End Managed Products |

> **The 2026 Reality:** Most enterprises are moving toward the **Agentic Software Factory** model to solve the "Maintenance Gap"—where AI agents are tasked with self-healing codebases, automatically detecting crashes, writing their own reproduction tests, and deploying hotfixes while human engineers focus on high-level system architecture.

Would you like me to create a detailed workflow for a specific Agentic SDLC role, such as how an "Agentic QA Engineer" operates compared to a traditional one?

[The Agentic Era](https://www.google.com/search?q=https://www.youtube.com/watch%3Fv%3DFqS_vj7-jYI)

This video provides an excellent high-level overview of how agentic workflows are replacing traditional software development patterns, aligning with the shift from reactive tools to proactive "digital co-workers."



# Appendix

- [ ] TODO: get an agent to mine more data and update this doc and make it better.

## interesting links and concepts. 

- https://github.com/coleam00/habit-tracker/blob/main/Top1%25AgenticEngineering.png
- https://github.com/humanlayer/12-factor-agents
- https://github.com/code-yeongyu/oh-my-opencode
- https://github.com/mitkox/ai-coding-factory
- https://monthofaibugs.com/


---
---

## Q: I want to build an AI powered Software Factory, but I keep getting non functional results. what do i need to learn to be successful.


Building an "AI Software Factory" that actually works requires moving beyond **one-shot generation** (where you ask for code and hope it runs) and into **agentic engineering**. The reason you are getting non-functional results is likely because your system lacks a "brain" for self-correction and a "body" to actually run and test the code.

To move from "cool prototypes" to "functional software," here is the learning path you need to master.

---

### 1. Agentic Design Patterns (The Architecture)

One-shot LLM prompts often fail because they try to solve too many things at once. Successful factories use a **multi-agent loop**. You need to learn how to orchestrate specialized agents.

* **The "Coder-Reviewer-Tester" Loop:** Don't just have an agent write code. Have an agent write the code, a second agent write the unit tests, a third agent **execute** those tests in a sandbox, and a fourth agent debug the failures.
* **Decomposition Skills:** Learn how to break a "Feature" into a "Plan," then "Tasks," then "Sub-tasks." AI excels at small, atomic units but loses coherence on large files.
* **State Management:** Learn how to use frameworks like **LangGraph** or **CrewAI** to maintain the state of a project (e.g., what files exist, which tests are currently failing, what the global architecture is).

### 2. Environmental Grounding (The Runtime)

If your AI can’t "see" the output of the code it wrote, it can't fix it. You need to build a **Runtime Sandbox**.

* **Code Execution Environments:** Learn tools like **E2B**, **Piston**, or **Docker** to create secure, isolated environments where the AI can run `npm install`, `pytest`, or `go build`.
* **Feedback Loops:** Instead of telling the AI "the code didn't work," your system must automatically capture **STDOUT** and **STDERR** and feed those logs back into the prompt.
* **LSPs (Language Server Protocols):** Learn how to integrate LSPs so the AI can perform "Go to Definition" or "Find References" across your entire codebase, just like a human in VS Code.

### 3. Repository RAG & Context Engineering

A major cause of non-functional code is the AI "hallucinating" functions or variables that don't exist in your specific project.

* **Codebase Indexing:** Learn how to use **Tree-sitter** or **LlamaIndex** to parse code into a syntax tree. This allows the AI to search for "relevant functions" rather than just keywords.
* **Context Pruning:** LLMs have limited "windows." You must learn how to automatically select only the files relevant to the current task to avoid overwhelming the model with irrelevant boilerplate.

### 4. Evaluation & Observability (The Quality Gate)

In a factory, you don't ship a car without an inspection. Your AI factory needs an automated "Quality Gate."

* **Automated Verifiers:** Learn to use static analysis tools (**SonarQube**, **ESLint**, **Pylint**) as "hard constraints" that must pass before the AI is allowed to "submit" its work.
* **LLM-as-a-Judge:** Learn how to use a more powerful model (like GPT-4o or Claude 3.5 Sonnet) specifically to audit the logic of a smaller, faster coding model (like DeepSeek Coder).

---

## Your Technology Stack Checklist

| Category | What to Learn / Use |
| --- | --- |
| **Orchestration** | LangGraph, CrewAI, or AutoGen |
| **Execution** | E2B (Sandboxed Cloud Runtime) or Docker |
| **Code Understanding** | Tree-sitter, Greptile (API for codebase RAG) |
| **Testing** | Pytest, Jest, or Keploy (for automated API testing) |
| **Observability** | LangSmith or Arize Phoenix (to see where the agents "get lost") |

---

### Recommended Next Step

To stop the "non-functional" cycle immediately, I recommend you look into **Test-Driven Development (TDD) for AI**.

'''
Test-Driven Development (TDD) for AI applies the traditional "Red, Green, Refactor" cycle to AI development, using automated tests to guide the creation of reliable AI agents, ensuring they meet functional specs, reducing errors, and improving code quality by having the AI test its own generated code or using AI to help write tests for human-coded AI features, making development faster and more robust. It involves writing failing tests first (Red), writing minimal code to pass them (Green), and then cleaning up (Refactor), with GenAI assisting in generating code, stubs, or even feedback loops. 
'''

## Q2: I want to constrain my AI Software Factory to Golang, where should i use automation and templates and where should i use agents, help me break it down.

To build an efficient AI Software Factory specifically for Golang, you must lean into Go's strengths: **predictability, strong typing, and standard formatting.** In a Go-centric factory, **Automation** handles the rigid "scaffolding" and "boilerplate" that Go is famous (or infamous) for, while **Agents** handle the high-level logic and complex concurrency patterns where human-like reasoning is needed.

---

## 🏗️ The Go Factory Breakdown

### 1. Automation & Templates (The "Skeleton")

Use these for deterministic tasks where the output should always follow the same structural rules.

| Area | What to Automate/Template | Why in Go? |
| --- | --- | --- |
| **Project Scaffolding** | Directory layout (`/cmd`, `/internal`, `/pkg`). | Go has a "standard" layout that avoids circular dependencies. Templates ensure consistency across services. |
| **Data Models** | Struct tags (JSON, BSON, XML), DB schemas, and Protobuf generation. | Go’s reflection-based tags are repetitive. Automation ensures `snake_case` or `camelCase` matches perfectly. |
| **API Routers** | Interface stubs and HTTP handler signatures (using `oapi-codegen` or similar). | Creating 50 boilerplate handlers for a REST API is a waste of an Agent’s tokens. |
| **Mocking** | Generating mock implementations for interfaces (using `mockgen`). | Go’s implicit interfaces make mocking highly predictable and automatable. |

### 2. AI Agents (The "Brain")

Use agents for non-deterministic tasks that require understanding the "intent" of the code.

* **Logical Implementation:** Task an agent with writing the actual body of a function (e.g., *"Write a thread-safe worker pool that processes these jobs using channels"*).
* **Context-Aware Refactoring:** Agents excel at identifying where a complex `if/else` chain should be refactored into a `switch` or a strategy pattern.
* **Concurrency Orchestration:** Go’s `goroutines` and `select` statements are powerful but easy to mess up (deadlocks). Agents are better at reasoning through the lifecycle of a channel than a static template.
* **Self-Healing/Debugging:** If the Go compiler throws a `nil pointer dereference` or a type mismatch, an agent can ingest the error, trace the pointer logic, and fix the implementation autonomously.

---

## 🛠️ The 2026 "Go-Native" Stack

To make this work in production, you should move away from generic Python-based AI frameworks and use Go-native tools to keep your factory lightweight and performant.

* **Framework:** **Eino (by ByteDance)** or **Google ADK for Go**. These allow you to build agentic chains directly in Go.
* **Interface-First Design:** Train your agents to always write the **Interface** first. This allows your Automation to immediately generate the Mocks and the Skeleton while the Agent continues working on the Implementation.
* **Strict Linting as a Guardrail:** Every Agent-generated snippet must pass through `golangci-lint` automatically. If it fails, the "Agent" receives the linting report as feedback to self-correct.

> **Pro Tip:** In Go, "simple is better than clever." Instruct your Agents to avoid deep nesting and to use the "Return Early" pattern. This makes the code they generate much easier for your automated testers to verify.

---

### Recommended Next Step

Would you like me to generate a **Go-specific System Prompt** that you can use to prime an Agent to follow the "Standard Go Project Layout" and strict error-handling patterns?

[Eino: The Golang AI LLM Framework You Should Learn in 2026](https://www.youtube.com/watch?v=_Cw11aRhcBQ)
This video is relevant because it introduces a production-ready, Go-native framework designed specifically for building agentic workflows, which is the missing link for your Go-only software factory.

- https://github.com/cloudwego/eino



---
---

## Q: Who has a AI golang software factory thats fully functional 

The term **"AI software factory"** refers to a new generation of development environments where autonomous AI agents, rather than human developers, handle the bulk of the software development lifecycle (SDLC)—from requirement gathering to deployment.

As of early 2026, several companies and projects have "fully functional" implementations that specifically leverage **Golang** due to its high performance and suitability for AI-driven microservices.

### 1. Cogna (The Lead Enterprise Factory)

**Cogna** is currently the most prominent company marketing a "fully functional" AI-powered Software Factory.

* **Focus:** They build bespoke digital tools for "traditional" industries like utilities, logistics, and manufacturing.
* **Golang Integration:** Their backend infrastructure and the "brain" of their factory are built using **Go**, Rust, and Python. They use agentic pipelines to generate code, run tests, and deploy applications to enterprise systems (SAP, Oracle).
* **Status:** Active and commercially operational with significant VC backing.

### 2. 8090 (Chamath Palihapitiya's Venture)

In late 2025, venture capitalist Chamath Palihapitiya launched **8090**, an incubator whose centerpiece is the **"Software Factory."**

* **Goal:** To enable "solo founders" to build billion-dollar software products without an engineering team.
* **Capabilities:** It automates full-cycle production, including architectural design and deployment. Because it targets high-performance enterprise apps, **Go** is a primary output and infrastructure language for its generated products.

### 3. Diffgram / Anthony Chaudhary (The "Internal" Factory)

**Diffgram** (an AI data platform) implemented what they call an **"AI Factory"** to manage their own production.

* **Proof of Concept:** In 2025, they published a case study on scaling autonomous agents to handle **2,000 real engineering issues in 30 days**.
* **Tech Stack:** Their system is heavily optimized for **Go-based microservices** on Google Cloud Platform (GCP). It is widely cited as the blueprint for "self-introspecting" software factories that review their own logs and fix their own bugs.

### 4. 1Sphere AI

**1Sphere** positions itself as an AI software factory specifically for Fortune 500 companies.

* **The Model:** They ship full platform components (auth, APIs, connectors) in 90-day sprints using AI orchestrators.
* **Go Focus:** They emphasize building high-throughput, "AI-native" API ecosystems where Go’s concurrency is the backbone.

### 5. Open Source: Anyi Framework

If you are looking for the *tools* to build your own Go-based software factory, **Anyi** is the leading open-source project.

* **What it is:** A Golang-based autonomous AI agent framework.
* **Use Case:** It allows you to define workflows (code generation, validation, command execution) in YAML or Go code to automate real work.

---

### Comparison of Functional "Factories"

| Entity | Primary Audience | Core Language Usage | Status |
| --- | --- | --- | --- |
| **Cogna** | Industrial/Enterprise | Go, Rust, Python | Fully Functional |
| **8090 (8090.ai)** | Solo Founders | Multi-language (Go heavy) | Launched Sept 2025 |
| **Diffgram** | Internal Development | Go | Operational |
| **1Sphere** | Fortune 500 | Go, TypeScript | Operational |
| **Anyi (GitHub)** | Developers | Go (written in & for) | Open Source |

---
---

## Q: Whats a native golang framework for building stateful agents with memory?

For building stateful agents with memory natively in Go, the ecosystem has matured significantly. Unlike Python, where a few giants dominate, the Go space is characterized by high-performance, type-safe frameworks designed for production-grade orchestration.

Here are the top native Golang frameworks for building stateful agents with memory:

---

## 1. Google Agent Development Kit (ADK)

Google’s ADK for Go is one of the most robust "native" options. It is designed for complex, hierarchical systems where agents need to maintain state across multiple turns and delegate tasks to others.

* **Memory Implementation:** It uses a `SessionService` to manage state. You can choose from `InMemory` (for prototyping) or `VertexAiMemoryBankService` for long-term persistence.
* **State Management:** Built-in support for session-aware routing, allowing agents to "remember" previous interactions within a specific thread.
* **Best For:** Enterprise-grade multi-agent systems and Google Cloud/Vertex AI users.

## 2. go-agent (by Protocol-Lattice)

This is a modular framework focused on "graph-aware" memory and orchestration. It is highly idiomatic and leverages Go's concurrency model.

* **Memory Implementation:** Features a multi-layered memory engine that supports **Importance Scoring** and **MMR Retrieval** (Maximal Marginal Relevance) to ensure the agent retrieves diverse and relevant context.
* **Backends:** Pluggable support for PostgreSQL+pgvector, Qdrant, MongoDB, and Neo4j.
* **State Management:** It uses a session-based approach where the entire reasoning trajectory is stored, making agents highly auditable.

## 3. trpc-agent-go

Developed within the tRPC ecosystem, this framework is built for high-scale agentic systems that require persistent state and complex reasoning.

* **Memory Implementation:** Offers an advanced memory system with persistent state management. It separates "Memory" (chat history) from "Knowledge" (RAG-based long-term facts).
* **State Management:** Supports graph-based workflows where the "State" is a shared object flowing through nodes, similar to LangGraph but written natively in Go.
* **Best For:** High-concurrency production environments and microservices architectures.

## 4. AgenticGoKit

This is a newer, streaming-first framework that emphasizes developer productivity and "batteries-included" features.

* **Memory Implementation:** Comes with **Chromem** (an embedded vector DB for Go) out-of-the-box, allowing you to add long-term memory to agents without setting up external infrastructure.
* **State Management:** Automatically manages session persistence and tool-call history.
* **Best For:** Rapid prototyping and local-first agent applications.

---

### Comparison Table

| Framework | Memory Type | Primary Storage | Key Strength |
| --- | --- | --- | --- |
| **Google ADK** | Session & Bank | Vertex AI / In-Memory | Official Google support, multi-agent hierarchy. |
| **go-agent** | Graph & Vector | pgvector, Qdrant, Neo4j | Sophisticated retrieval (MMR), very modular. |
| **trpc-agent-go** | Persistent & Graph | Pluggable (DB-backed) | High-performance, graph-based state flow. |
| **AgenticGoKit** | Vector (Embedded) | Chromem (Local) | Easiest setup, local-first long-term memory. |

### A Note on "Native" vs. "Port"

While **LangChainGo** exists, it is often viewed as a port of the Python library. If you want a framework that feels like "real Go"—leveraging interfaces, goroutines, and strict typing—the options above (specifically **Google ADK** and **go-agent**) are generally preferred by Gophers.

**Would you like me to provide a code example for setting up a persistent memory store using one of these frameworks?**

[Go AI Agent Implementation Guide](https://www.youtube.com/watch?v=MvZTKDQmImQ)
This video provides a deep dive into building agentic AI frameworks natively in Go, focusing on the architectural advantages of using Go for production-grade stateful agents.



