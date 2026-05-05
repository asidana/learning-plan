# 🧠 Learning Notes: Evaluation-Driven Development (EDD) for Agents

**Sources:** Synthesis of Hamel Husain, Jason Liu (6 RAG Evals), and Nous Group (The Evaluation Imperative).

## 📌 The Core Thesis
Transitioning from "Prompt Engineering" to "AI Architecture" requires adopting **Evaluation-Driven Development (EDD)**. You cannot build a reliable agentic system by "vibing" with prompts. You must define success mathematically before writing code, prioritizing **Surgical Evaluation** over generic metrics.

---

## 🛠️ The EDD Framework

### 1. The 6 Definitive RAG Evals
Instead of generic "similarity" scores, measure the specific relationships between **Question (Q)**, **Context (C)**, and **Answer (A)**:
*   **Context Relevance ($C \mid Q$):** Does retrieved data actually address the question?
*   **Faithfulness ($A \mid C$):** Is the answer derived *exclusively* from the context? (The Hallucination Guard).
*   **Answer Relevance ($A \mid Q$):** Does the answer satisfy the user's intent?
*   **Context Support ($C \mid A$):** Is there enough evidence in the context to justify every claim made in the answer?
*   **Question Answerability ($Q \mid C$):** Can the question even be answered with what was retrieved?
*   **Retrieval Recall ($C_{true} \mid Q$):** Did we find the ground-truth document?

### 2. Binary Precision over Likert Noise
*   **The Rule:** Stop using 1-5 scales for LLM judges. They are inconsistent and mathematically noisy.
*   **The Fix:** Use **Binary (Pass/Fail) Evals**. An answer is either faithful to the context or it isn't. This provides the clean signal required for automated regression testing in CI/CD.

### 3. Small Gold Datasets > Synthetic Volume
*   **The Strategy:** Do not start with 1,000 synthetic examples. Start with **20 high-quality, human-verified "Gold" cases**. 
*   **Calibration:** Use these 20 cases to "test your tester." Ensure your automated LLM-as-a-Judge agrees with human experts 100% of the time on these cases before scaling.

---

## 🧭 The Leadership Layer: Conversational Capital
Beyond mathematical RAG metrics, architects must evaluate the **Trust Ledger** of the interaction.

1.  **Deposits:** Interactions that earn trust through empathy, proactive honesty ("I don't know the answer, let me find a human"), and clear resolution.
2.  **Withdrawals:** Interactions that destroy trust through faked confidence, robotic ignorance of user emotion, or circular loops.
3.  **The Axiom:** In Agentic AI, neutral interactions do not exist. You are either building brand equity or accruing "content debt."

---

## 🏛️ Enterprise Impact: Avoiding "Workslop"
The Nous Group research warns that high AI adoption metrics often mask **"Workslop"**—low-value AI content that creates more work for human reviewers.

### 5 Domains of AI Maturity ( Nous Group Model):
1.  **Adoption Capability:** Real proficiency vs. simple license usage.
2.  **System Performance:** Seamless data estate integration.
3.  **Governance & Risk:** Verifiable guardrails and authority.
4.  **Value Delivery:** Separating "time saved" from "quality improved."
5.  **Competitiveness:** Maturity compared to sector benchmarks.

---
*Tags: #EDD #AIEvals #RAG #Governance #EnterpriseAI #Workslop*