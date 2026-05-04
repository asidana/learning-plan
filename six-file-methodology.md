# 🧠 Learning Notes: The "Six-File Methodology" for AI Engineering

**Source:** [How Senior Engineers Actually Build With AI in 2026 (JS Mastery)](https://www.youtube.com/watch?v=14RP8liACqo)

## 📌 The Core Thesis
The transition from a "Junior Prompt Engineer" to a "Senior AI Architect" requires shifting from chat-based trial-and-error to **Spec-Driven Development**. Senior engineers do not ask an AI to "build a feature." They curate a rigid, multi-file context window that forces the AI to act within strict architectural boundaries.

---

## 🛠️ The Six-File Methodology

To get deterministic, production-grade results from an AI coding agent (like Claude Code, Cursor, or your custom CLI), you must maintain these six living documents in your project's root or `.agent/` folder:

### 1. `product_spec.md`
*   **Purpose:** The "Why." 
*   **Content:** Defines the user personas, the core problem being solved, the business logic, and the high-level features. Keeps the AI from hallucinating scope creep.

### 2. `tech_stack.md`
*   **Purpose:** The "How."
*   **Content:** An explicit list of libraries, frameworks, and exact version numbers (e.g., Next.js 15, TailwindCSS v4, Zustand). Prevents the AI from importing deprecated packages.

### 3. `file_structure.md`
*   **Purpose:** The "Where."
*   **Content:** A mapped-out tree of the repository. Prevents the AI from randomly creating `src/utils/` when your team convention uses `src/lib/`.

### 4. `frontend_spec.md`
*   **Purpose:** The "Look & Feel."
*   **Content:** Detailed component breakdown, styling tokens (Design DNA), routing paths, and state management rules for the UI.

### 5. `backend_spec.md`
*   **Purpose:** The "Data."
*   **Content:** Database schemas (Prisma/Drizzle models), API endpoint definitions, WebRTC/Socket orchestration rules, and authentication flows.

### 6. `rules.md` (or `CLAUDE.md`)
*   **Purpose:** The "Never Do This."
*   **Content:** Strict linters for the AI. (e.g., *"Never use any type 'any' in TypeScript,"* *"Always use absolute imports,"* *"Never use regular CSS, only Tailwind classes."*)

---
## 🚀 Architectural Impact
By establishing this six-file context, you change the AI's role from a "code generator" to an **"Architecture Reviewer."** The AI reads the spec, identifies structural gaps, and writes code that perfectly aligns with the established enterprise system design.

*Tags: #AgenticEngineering #SpecDrivenDevelopment #ContextManagement #AIAssistants*