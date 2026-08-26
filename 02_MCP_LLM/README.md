# AI Notes: LLM, GPT, Gemma 4, Claude, Agents, Tools & MCP

A practical guide to understanding **AI, LLMs, GPT, Gemma 4, Claude, Claude Code, AI Agents, Tools, MCP, and Ollama**.

---

## 1. What is AI?

**AI (Artificial Intelligence)** means making computers perform tasks that normally require human intelligence.

Examples:

* Understanding language
* Recognizing images
* Writing code
* Making decisions
* Planning tasks
* Answering questions

### Simple Idea

```text
Human Intelligence
        ↓
Computer System
        ↓
       AI
```

---

## 2. What is an LLM?

**LLM = Large Language Model**

An LLM is an AI model trained on a very large amount of data so it can understand and generate language.

Examples:

* GPT
* Claude
* Gemini
* Gemma
* Llama
* Mistral

### Basic Workflow

```text
Question
   ↓
  LLM
   ↓
Understand Context
   ↓
Generate Response
```

### Example

You ask:

> Write Python code to create an API.

The LLM may generate:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello World"
```

---

## 3. How does an LLM work?

At a simplified level:

```text
Training Data
     ↓
Tokenization
     ↓
Neural Network
     ↓
Training
     ↓
    LLM
     ↓
   Prompt
     ↓
   Tokens
     ↓
 Prediction
     ↓
  Response
```

The model learns statistical patterns from its training data.

It does **not** work like a traditional database that simply searches for an exact answer.

---

## 4. What does "Past Data" Mean?

An LLM has **training data**.

For example:

```text
Books
Web Pages
Code
Documents
Articles
Other Permitted Training Data
        ↓
      Training
        ↓
       LLM
```

After training, the model has learned patterns from that data.

### Important

**Training data ≠ Live Internet**

Suppose a model was trained before a new product was launched.

It may not know about that product unless:

1. The information is provided in its context.
2. It uses a search/browsing tool.
3. The model is later updated or retrained.

Therefore:

```text
Training Data
     ↓
What the Model Learned

Live Tools
     ↓
What the Model Can Obtain Now
```

This distinction is important for understanding AI agents.

---

# 5. What is GPT?

**GPT = Generative Pre-trained Transformer**

GPT refers to a family of generative Transformer-based models developed by OpenAI.

### Generative

It generates content such as:

```text
Text
Code
Summaries
Answers
```

### Pre-trained

The model is trained before you interact with it.

### Transformer

The model is based on the Transformer neural-network architecture.

Therefore:

```text
GPT
│
├── Generative
├── Pre-trained
└── Transformer
```

GPT is an **LLM/model family**, not a completely separate concept from an LLM.

---

# 6. What is Gemma 4?

**Gemma 4** is Google's family of open models from Google DeepMind.

Conceptually:

```text
Google
   ↓
Google DeepMind
   ↓
Gemma
   ↓
Gemma 4
```

Gemma models are designed for applications including reasoning and agentic workflows.

Examples of Gemma 4 model sizes include:

* E2B
* E4B
* 12B
* 26B
* 31B

---

# 7. Why use Ollama with Gemma 4?

**Ollama is not the LLM.**

Ollama is software that allows supported AI models to run locally on your computer.

```text
Ollama
   ↓
Runs
   ↓
Gemma 4
   ↓
Your Computer
```

For example:

```bash
ollama pull gemma4
```

Then:

```bash
ollama run gemma4
```

### Technology Comparison

| Technology  | What it is                  |
| ----------- | --------------------------- |
| Gemma 4     | LLM/model family            |
| Ollama      | Local model runtime         |
| Claude      | Anthropic's AI/model family |
| Claude Code | Coding agent                |
| MCP         | Connection protocol         |
| GPT         | OpenAI model family         |

---

# 8. What is Claude?

**Claude** is Anthropic's AI assistant and model family.

Conceptually:

```text
Anthropic
    ↓
  Claude
    ↓
  Models
   ├── Opus
   └── Sonnet
```

Claude models can be used for tasks such as:

* Coding
* Reasoning
* Writing
* Analysis
* Agentic workflows

---

# 9. What is Claude Code?

**Claude Code is an AI coding agent from Anthropic.**

It operates from the terminal and can work with a software project.

You can start the CLI with:

```bash
claude
```

A simplified workflow is:

```text
You
 ↓
Claude Code
 ↓
Read Project
 ↓
Understand Code
 ↓
Plan Change
 ↓
Edit Files
 ↓
Run Commands / Tests
 ↓
Report Result
```

This is more powerful than simply asking an LLM:

> Write me some Python code.

---

# 10. Claude Opus vs Sonnet

Think of **Opus** and **Sonnet** as different Claude model tiers.

### Claude Opus

Generally aimed at more difficult reasoning and complex, long-running tasks.

### Claude Sonnet

Designed to provide a strong balance of:

* Intelligence
* Coding ability
* Speed
* Cost

---

# 11. Claude Opus

Claude Opus models are designed for demanding tasks such as:

* Advanced coding
* Complex reasoning
* Large codebases
* Debugging
* Code review
* Long-running agentic workflows

---

# 12. Claude Sonnet

Claude Sonnet models are designed for tasks such as:

```text
Coding
Computer Use
Reasoning
Agent Planning
Long Context
Professional Work
```

The exact capabilities and model versions can change over time, so current model documentation should be checked when discussing specific releases.

---

# 13. What is Agentic AI?

This is one of the most important concepts.

### Normal LLM

```text
Question
   ↓
 LLM
   ↓
Answer
```

### Agentic AI

```text
Goal
 ↓
Agent
 ↓
Plan
 ↓
Use Tools
 ↓
Observe Results
 ↓
Reason
 ↓
Take Next Action
 ↓
Verify
 ↓
Complete Goal
```

The important difference is:

> **Action + Planning + Iteration**

---

# 14. Simple Example of Agentic AI

You tell a coding agent:

> Find the bug in my application and fix it.

A coding agent might:

```text
1. Inspect Project
       ↓
2. Find Relevant Files
       ↓
3. Understand Code
       ↓
4. Identify Possible Bug
       ↓
5. Modify Code
       ↓
6. Run Tests
       ↓
7. Test Fails
       ↓
8. Analyze Failure
       ↓
9. Modify Code Again
       ↓
10. Run Tests
       ↓
11. Tests Pass
       ↓
12. Report Result
```

This is an **agentic workflow**.

---

# 15. What is an AI Agent?

An **AI agent** is a system that combines an LLM with instructions, context, tools, and an execution mechanism to take actions toward a goal.

### Simplified Architecture

```text
              ┌──────────────┐
              │     User     │
              └──────┬───────┘
                     ↓
              ┌──────────────┐
              │    Agent     │
              └──────┬───────┘
                     ↓
              ┌──────────────┐
              │     LLM      │
              └──────┬───────┘
                     ↓
          ┌──────────┼──────────┐
          ↓          ↓          ↓
       Search       Code      Database
        Tool        Tool        Tool
```

---

# 16. What are Tools?

A **tool** gives an AI system the ability to perform actions outside the model itself.

Examples:

```text
LLM
 │
 ├── Web Search
 ├── Calculator
 ├── Terminal
 ├── File System
 ├── Git
 ├── Database
 ├── API
 └── Browser
```

### Without Tools

The LLM primarily generates responses from the information available in its context and learned parameters.

### With Tools

The AI system can perform external actions.

Example:

```text
User
 ↓
Agent
 ↓
Database Tool
 ↓
Database
 ↓
Results
 ↓
LLM
 ↓
Answer
```

---

# 17. What is MCP?

**MCP = Model Context Protocol**

MCP is an open protocol that standardizes how AI applications connect to external data, tools, and services.

A useful analogy is:

> **MCP is like USB-C for AI applications.**

Instead of building a completely different integration for every AI application and service:

```text
AI → GitHub
AI → Database
AI → Slack
AI → Files
AI → Google Drive
```

MCP provides a standardized connection approach.

```text
                 MCP
                  │
        ┌─────────┼─────────┐
        ↓         ↓         ↓
     GitHub    Database    Files
```

### Important

**MCP is not an LLM.**

MCP is a **protocol/connection layer**.

---

# 18. Three Important MCP Concepts

MCP commonly exposes three major primitives:

## 18.1 Tools

Tools are functions that an AI application can invoke.

Examples:

```text
create_file()
search_database()
get_weather()
create_github_issue()
```

Tools can allow an AI application to:

* Query databases
* Call APIs
* Perform calculations
* Modify files
* Perform external actions

---

## 18.2 Resources

Resources provide information or context to the AI application.

Examples:

```text
Files
Database Schemas
Documentation
Git History
```

---

## 18.3 Prompts

Prompts are reusable prompt templates or workflows exposed through MCP.

---

# 19. MCP Architecture

```text
                    USER
                      │
                      ↓
                Claude Code
                      │
                      ↓
                    LLM
                      │
                      ↓
                  MCP Client
                      │
                 MCP Protocol
                      │
        ┌─────────────┼─────────────┐
        ↓             ↓             ↓
   MCP Server     MCP Server     MCP Server
     GitHub         Database        Files
        ↓             ↓             ↓
    GitHub DB      PostgreSQL    Local Files
```

The MCP client communicates with MCP servers through the MCP protocol.

---

# 20. LLM + Tools + Agent + MCP

This is the most important architecture to remember:

```text
                    USER
                      │
                      ↓
                   AGENT
                      │
                      ↓
                    LLM
                      │
              ┌───────┴────────┐
              ↓                ↓
          Reasoning           Tools
                                │
                                ↓
                               MCP
                                │
             ┌──────────────────┼────────────────┐
             ↓                  ↓                ↓
          GitHub             Database          Files
```

---

# 21. Where Does Gemma 4 Fit?

Gemma 4 is the **LLM/model layer**.

A conceptual workflow could be:

```text
User
 ↓
Agent
 ↓
Gemma 4
 ↓
Tool Decision
 ↓
MCP
 ↓
Tool
 ↓
Result
 ↓
Gemma 4
 ↓
Final Answer
```

Ollama can provide the local runtime for a supported model.

```text
Agent
  ↓
Ollama
  ↓
Gemma 4
```

---

# 22. Where Does Claude Code Fit?

Claude Code is the **coding-agent application layer**.

```text
                 Claude Code
                      │
          ┌───────────┼───────────┐
          ↓           ↓           ↓
         LLM        Tools        MCP
          │           │           │
       Reasoning    Terminal    External
                    Files       Services
                    Git
```

This is why Claude Code is different from simply asking an LLM:

> Write some code.

A coding agent can interact with the project, use tools, execute commands, inspect results, and iterate.

---

# 23. Complete Example

Suppose you have a software project.

You tell your agent:

> Check my application, find why it is unhealthy, fix the configuration, and test it.

A possible workflow:

```text
User
 │
 ↓
AI Agent
 │
 ↓
LLM
 │
 ├──── Kubernetes Tool
 │
 ├──── Terminal Tool
 │
 ├──── File Tool
 │
 └──── MCP
          │
          ├── Kubernetes
          ├── GitHub
          └── Database
```

The agent can then:

```text
Read Configuration
       ↓
Check Application Status
       ↓
Find Configuration Problem
       ↓
Edit Configuration
       ↓
Run Commands
       ↓
Check Application
       ↓
Run Tests
       ↓
Verify Result
       ↓
Report Result
```

This demonstrates:

**Agentic AI + LLM + Tools + MCP**

---

# 24. Model vs Agent vs Tool vs MCP

| Concept         | Meaning                                               | Example                    |
| --------------- | ----------------------------------------------------- | -------------------------- |
| **LLM**         | Large language model                                  | Gemma, GPT, Claude         |
| **GPT**         | OpenAI model family                                   | GPT models                 |
| **Gemma 4**     | Google's model family                                 | Gemma models               |
| **Claude**      | Anthropic's AI/model family                           | Claude Opus/Sonnet         |
| **Claude Code** | Coding-agent application                              | `claude` CLI               |
| **Agent**       | System that reasons, plans, and acts                  | Coding agent               |
| **Tool**        | Capability/action available to an agent               | Terminal, search, database |
| **MCP**         | Protocol for connecting AI applications to tools/data | GitHub MCP server          |
| **Ollama**      | Local model runtime                                   | `ollama run gemma4`        |

---

# 25. The Easiest Way to Remember Everything

Think of an **AI Software Engineer**:

```text
                    YOU
                     │
                     ↓
                  AGENT
                     │
                     ↓
                   LLM
              "The Brain"
                     │
        ┌────────────┼────────────┐
        ↓            ↓            ↓
      THINK        TOOLS        CONTEXT
        │            │            │
        │         Terminal       MCP
        │         Git            │
        │         Browser        │
        │         Database       │
        │                         │
        └───────────┬─────────────┘
                    ↓
                  ACTION
                    ↓
               OBSERVATION
                    ↓
                  THINK
                    ↓
                  ACTION
                    ↓
                  RESULT
```

---

# 26. One-Line Definitions for Interviews

### LLM

> An LLM is a large AI model trained on large amounts of data to understand and generate language.

### GPT

> GPT stands for Generative Pre-trained Transformer and refers to OpenAI's family of generative Transformer-based models.

### Gemma 4

> Gemma 4 is Google's family of open AI models designed for tasks such as reasoning and agentic workflows.

### Agentic AI

> Agentic AI is an AI system that can reason about a goal, plan steps, use tools, observe results, and take further actions.

### Agent

> An AI agent combines an LLM with instructions, context, tools, and an execution loop to accomplish a goal.

### Tool

> A tool gives an AI agent the ability to perform an external action, such as running commands, searching the web, querying a database, or modifying files.

### MCP

> MCP is an open protocol that standardizes how AI applications connect to external tools and data.

### Claude Code

> Claude Code is Anthropic's coding agent that operates from the terminal and can understand a codebase, edit files, run commands, use tools, and work with MCP servers.

### Ollama

> Ollama is a runtime that allows developers to run supported AI models locally.

---

# 27. Big Picture

The entire topic can be remembered as:

```text
                 AI APPLICATION
                       │
                       ↓
                    AGENT
                       │
                       ↓
                     LLM
          ┌────────────┼────────────┐
          ↓            ↓            ↓
       Reasoning     Context       Tools
          │            │            │
          │           MCP           │
          │            │            │
          │      ┌─────┴─────┐      │
          │      ↓           ↓      │
          │   Resources    Tools    │
          │                         │
          └────────────┬────────────┘
                       ↓
                     ACTION
                       ↓
                  OBSERVATION
                       ↓
                     LLM
                       ↓
                    RESULT
```

---

# 28. Final Mental Model

Remember these five layers:

```text
1. AI
   ↓
2. LLM
   ↓
3. Agent
   ↓
4. Tools
   ↓
5. MCP
```

More precisely:

```text
AI Application
      │
      ↓
    Agent
      │
      ↓
     LLM
      │
      ├──────── Reasoning
      │
      ├──────── Context
      │
      └──────── Tools
                   │
                   ↓
                  MCP
                   │
          ┌────────┼────────┐
          ↓        ↓        ↓
       GitHub   Database   Files
```

### The key idea

**LLM = Brain**

**Agent = Brain + Goal + Instructions + Execution Loop**

**Tool = Ability to Take Action**

**MCP = Standardized Way to Connect AI Applications with Tools and Data**

**Ollama = Runtime for Running Supported Models Locally**

**Claude Code = Coding Agent Application**

**Gemma 4 / GPT / Claude = Model Families**
