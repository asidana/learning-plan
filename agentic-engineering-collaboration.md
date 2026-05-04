# 🧠 Learning Notes: Agentic Engineering – Working With AI, Not Just Using It

**Source:** "Agentic Engineering: Working With AI, Not Just Using It" by Brendan O'Leary (Kilo Code)

## 📌 The Core Thesis
The era of "vibe coding" (blindly prompting an LLM to generate entire applications) is ending for serious software development. To build production-grade software with AI, engineers must transition from treating AI as an unpredictable "copilot" to a constrained, reliable collaborator. The key to this transition is **Ruthless Context Management**.

---

## 🛠️ Key Takeaways & Architectural Applications

### 1. The Fallacy of "More Context is Better"
*   **The Problem:** Shoving an entire codebase into an agent's context window actually degrades its performance. Bad or excessive context corrupts the AI's reasoning, leading to scope creep and hallucinations.
*   **The Solution:** Use **Selective Context**. Engineers must curate the exact files, specific terminal outputs, and relevant commits needed for the immediate step.

### 2. Standardized Agent Configuration (`agents.md`)
*   **The Strategy:** Do not rely on hidden IDE settings or global system prompts. Use an `agents.md` (or `CLAUDE.md`) file to explicitly define:
    *   The agent's long-term project context.
    *   What tools the agent is permitted to use autonomously (e.g., reading files, running linters).
    *   What actions strictly require human approval (e.g., database migrations, Git pushes).
*   **The Impact:** This creates a version-controlled, team-wide standard for how AI agents behave within a specific repository.

### 3. State Management via "Scratchpads"
*   Agents lack native internal memory for long-running tasks. 
*   **The Architectural Fix:** Force the agent to maintain a temporary markdown file (a "Scratchpad") to track its current plan, completed steps, and pending issues. This prevents the agent from losing the plot during multi-turn coding sessions.

### 4. Specialized Modes (Role-Based AI)
*   Do not use a "General" agent for everything. Configure explicit roles:
    *   **Architect:** Analyzes the `agents.md` and generates a plan.
    *   **Ask/Researcher:** Greps the codebase to answer specific questions.
    *   **Code/Implementer:** Strictly executes the Architect's plan without inventing new features.

---
*Tags: #AgenticEngineering #ContextManagement #AIAssistants #Workflow #DeveloperExperience*