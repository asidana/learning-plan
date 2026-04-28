# 🧠 Learning Notes: The QRPSI Workflow

**Video Source:** [Everything We Got Wrong About Research-Plan-Implement (Dexter Horthy)](https://www.youtube.com/watch?v=YwZR6tc7qYg)

## 📌 The Core Thesis
The standard **Research-Plan-Implement (RPI)** agentic workflow is broken because it encourages software engineers to outsource their architectural thinking to AI. True agentic engineering requires strict human oversight, structured artifacts, and extreme context management.

The new proposed workflow is **QRPSI**: *Query -> Research -> Plan -> Summarize -> Implement*.

---

## 🛠️ Key Takeaways & Best Practices

### 1. Do Not Outsource the "Thinking"
* The biggest failure mode in AI coding is letting agents make critical architectural decisions autonomously.
* **The "Design Concept":** Force the agent to "brain dump" its research into a ~200-line Markdown artifact. The human engineer then reviews and performs "brain surgery" on this document *before* the agent writes a single line of code.

### 2. Ruthless Context Window Management
* Keep context utilization **under 30-40%** for optimal reasoning.
* If context usage exceeds 60%, the LLM begins to suffer from "degrading results" and will routinely fail to follow strict system instructions.
* **Beware Instruction Bloat:** Providing an agent with too many tools or MCP (Model Context Protocol) servers distracts it from the core coding task. Strip down the environment to only what is absolutely necessary for the specific objective.

### 3. Vertical Slicing for Agents
* Instead of broad, horizontal repository searches (which blow up the context window), dispatch sub-agents through "deep vertical slices" of the codebase.
* Their goal is to gather *objective truths* about how the current system works and return a highly compressed summary to the main planner agent.

### 4. Structure > "Magic Prompts"
* Stop relying on "vibes" and perfectly worded prompts. 
* Reliability comes from rigid, structured workflows that physically force alignment between the human's intent and the agent's execution phase.

---
*Tags: #AgenticWorkflows #SoftwareArchitecture #ContextManagement #QRPSI*
