# 🧠 Learning Notes: Agent Evaluation as Security Audit

**Source:** [Why Your Agent Eval Suite is a Security Audit, Not a QA Exercise](https://www.linkedin.com/pulse/why-your-agent-eval-suite-security-audit-qa-exercise-veyon-solution-p3ftc/)

## 📌 The Core Thesis
Traditional QA assumes a stable input distribution and known failure modes. AI agents, however, operate on arbitrary natural language and have access to powerful tools, making them vulnerable to **Adversarial Threats** (prompt injection, tool data exfiltration). Evaluating an agent is not just about "does it work," but "is it safe?"

---

## 🛠️ Key Takeaways & Architectural Applications

### 1. Adversarial vs. Stable Distributions
*   **The Issue:** Regression suites test if the code still does what it used to. Security audits test what the code *could* do under duress.
*   **The Architectural Fix:** Move evaluation responsibility from "Engineering Productivity" to "Security/Risk" teams. Focus on **Negative Testing** (trying to break the agent) rather than just validating happy paths.

### 2. Rotational Evaluation (The "Anti-Stale" Suite)
*   **The Issue:** Agents learn to "pass" static test sets, but fail when real-world adversarial probes drift.
*   **The Architectural Fix:** Implement **Release-Bound Red-Team Rotations**. Every 2–4 weeks, refresh the evaluation suite with new adversarial prompts and edge cases based on production traffic patterns.

### 3. Capability-Escape Rate
*   **New Metric:** Instead of a single pass/fail percentage, measure the **Capability-Escape Rate**—the frequency at which an agent bypasses its intended behavioral constraints to execute a restricted tool or access unauthorized data.

---
*Tags: #AIEvals #RedTeaming #AISecurity #Governance #RiskManagement*