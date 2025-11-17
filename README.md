# ADK Multi-Modal Agent — Resumable AI Workflows

### *Automated Multi-Step AI Workflow Management with Human-in-the-Loop Decision Making*

This project implements a **Resumable AI Agent** framework using Google’s **ADK**, demonstrating automated orchestration of complex workflows while allowing human intervention for critical decisions. It integrates **LlmAgents** with external MCP tools for tasks like image generation and shipping order processing, ensuring full workflow resumability.

---

## Features

### Shipping Coordinator Assistant

* Processes container shipping orders
* Automatically approves small shipments
* Pauses for human approval on large orders
* Implements pausable tools using **FunctionTool** and **ToolContext**
* Maintains workflow state for seamless resumption

### Multi-Modal Tool Integration

* Integrates MCP-based tools for dynamic image generation
* Supports human-in-the-loop workflows
* Demonstrates multi-step task orchestration with AI agents

### Session & Workflow Management

* Uses **InMemorySessionService** and **Runner** for session handling
* Ensures reproducible, traceable interactions between user, AI decisions, and external tools
* Handles long-running tasks and conditional workflows robustly

---

## Core Architecture

| Component           | Description                                                |
| ------------------- | ---------------------------------------------------------- |
| **Agents**          | LlmAgents orchestrating multi-step operations              |
| **Tools**           | MCP Tools for image generation and task automation         |
| **Pausable Tools**  | FunctionTool + ToolContext for human-in-the-loop approvals |
| **Session Service** | InMemorySessionService for managing workflow states        |
| **Runner**          | Executes agents and resumes workflows reliably             |
| **Framework**       | Google ADK, Gemini LLM, Python                             |

---

## Usage

### Step 1 — Initialize Resumable App

```python
shipping_app = App(
    name="shipping_coordinator",
    root_agent=shipping_agent,
    resumability_config=ResumabilityConfig(is_resumable=True),
)
```

### Step 2 — Run Workflow

```python
await run_shipping_workflow("Ship 10 containers to Rotterdam", auto_approve=True)
```

### Step 3 — Human-in-the-Loop Decision

* Large orders are paused for approval
* Responses resume workflow seamlessly after human input

---

## Results

* Efficient multi-step task automation
* Human-in-the-loop approval handling
* Traceable sessions and reproducible outputs
* Multi-modal AI agent demonstrating dynamic tool integration

---

## Tools & Techniques

Python, Google ADK, Gemini LLM, MCP Tools, LlmAgent, FunctionTool, Resumable Apps, Human-in-the-Loop AI, Session Management, Workflow Orchestration, Image Generation, Automation, Multi-step Task Handling

---

## Author

Abdullah

* GitHub: [github.com/chabdullah7](https://github.com/chabdullah7)
* LinkedIn: [linkedin.com/in/ch-abdullah-b537951a](https://www.linkedin.com/in/ch-abdullah-b537951a)
