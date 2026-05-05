# 🧠 Learning Notes: Agentic QA & Evaluation Trends (2026)

**Source:** Synthesis of 2026 industry research on Agentic QA, Business Use Case Testing, and the "Evaluation-Led" Framework.

## 📌 The Core Thesis
Evaluation remains the "Hardest Part" of AI systems because probabilistic outputs cannot be validated by static scripts. In 2026, the industry has shifted from **Functional Testing** (checking if the code runs) to **Agentic QA** (verifying if the agent makes the right decisions across multi-turn workflows). Success is now defined by **Risk Coverage** rather than code coverage.

---

## 🛠️ The 2026 Best Approach: The "Evaluation-Led" Framework

### 1. From Task to Workflow Testing
*   **The Shift:** Stop testing single prompts. Start testing **Trajectories**. 
*   **Focus:** Can the agent plan, select tools, and self-correct across a 10-turn conversation?
*   **Key Metric:** *Branching Accuracy*—did the agent take the correct logical path when faced with an ambiguity?

### 2. Risk Coverage over Test Coverage
*   **The Reality:** With 40%+ of code being AI-generated, 100% test coverage is a pipe dream.
*   **The Strategy:** Identify "High-Stakes Decision Points" (e.g., executing a bank transfer, updating a medical record). Prioritize 100% evaluation for these risky actions while allowing "vibe-based" lower-priority UX features.

### 3. The 3-Layer Instrumentation (Reasoning, Action, Safety)
| Layer | Architectural Focus | Standard Metric |
| :--- | :--- | :--- |
| **Reasoning** | The Agent's internal "thinking" loop. | Plan Quality Score (LLM-as-a-Judge) |
| **Action** | Tool calls and parameter accuracy. | Tool Success Rate (Deterministic) |
| **Safety** | Guardrails and compliance. | Capability-Escape Rate (Red-Teaming) |

### 4. Reliability Loops (Failures as Data)
*   **The Concept:** Production failures are the most valuable evaluation data.
*   **The Workflow:** When an agent fails in production, the trace is automatically captured, anonymized, and injected into the **Golden Truth Dataset** as a new regression test case.

---

## 🚀 Business Use Case Priorities
*   **Concierge Agents:** Focus on "Resolution Metrics." Did the user actually get the refund?
*   **FinOps Agents:** Focus on "Auditability." Is every step of the KYC process cryptographically signed and explainable?
*   **DevOps Agents:** Focus on "Deterministic Execution." Does the generated patch actually pass the build?

---
*Tags: #AgenticQA #AIEvals #SDLC2026 #ReliabilityEngineering #RiskCoverage*