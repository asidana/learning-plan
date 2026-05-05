# 🧠 Learning Notes: Multidimensional AI Quality – Beyond Accuracy

**Source:** Insights on AI Evals and Judgment Systems.

## 📌 The Core Thesis
In traditional ML, quality is a number (Accuracy, Precision, Recall). In GenAI, **Accuracy is not enough.** A response can be factually correct but irrelevant, fluent but useless, or helpful but unsafe. We must shift from **optimizing a single score** to **designing multidimensional judgment systems** that reflect how users actually perceive value.

---

## 🛠️ The 7 Dimensions of GenAI Quality

To measure if an agent "actually helped," we must evaluate across these vectors:

1.  **Intent Resolution:** Did the agent address the underlying problem or just the literal text?
2.  **Instruction Adherence:** Did the agent follow all constraints, formatting rules, and "never-do" patterns?
3.  **Relevance:** Did the response stay focused on the user's specific context?
4.  **Accuracy:** Is the information factually correct and trustworthy?
5.  **Completeness:** Were all required parts of the task addressed, or did it miss critical nuances?
6.  **Actionability:** Can the user actually *use* the output to take the next step (e.g., valid code, clear instructions)?
7.  **Safety:** Is the output responsible, unbiased, and free of PII or harmful content?

---

## 🚀 Architectural Impact: Evals as a Product Capability
*   **Judgment Systems:** Evals are no longer just a Data Science problem; they are a core Product capability.
*   **Telemetry Matters:** You cannot judge what you don't track. Full-stack telemetry (Reasoning traces, tool inputs/outputs, user feedback) is the fuel for multidimensional evals.
*   **Agent-Specific Evals:** A coding agent needs different metrics (Build pass rate) than a support agent (CSAT/Sentiment).
*   **Judicious LLM-as-a-Judge:** Use high-reasoning models to score these dimensions, but recognize where automated deterministic checks (e.g., regex, linting) are more reliable.

---
*Tags: #AIEvals #QualityEngineering #GenAI #SystemDesign #ProductManagement*