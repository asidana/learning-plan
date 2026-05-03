# 🧠 Learning Notes: The LLM Training Stack Decoded

**Source:** LinkedIn post on "The LLM Training Stack, Decoded" (Linas).

## 📌 The Core Thesis
Most engineers misuse the term "fine-tuning," often spending thousands of dollars and months of effort on full fine-tunes when a low-cost adapter would suffice. Understanding the difference between SFT, RLHF, DPO, and PEFT is what separates API wrappers from true AI Architects.

---

## 🛠️ Key Takeaways & Architectural Applications

### 1. SFT (Supervised Fine-Tuning)
*   **Concept:** Training on input-output pairs. This is the baseline. You show the model what "good" looks like, and it learns to mimic the format.
*   **Use Case:** Teaching an LLM to output a highly specific proprietary JSON schema.

### 2. RLHF (Reinforcement Learning from Human Feedback)
*   **Concept:** SFT teaches format; RLHF teaches *preference*. Humans rank outputs, and the model learns what "better" means.
*   **The Reality:** It is the gold standard for conversational models (like ChatGPT), but it is incredibly slow and expensive.

### 3. DPO (Direct Preference Optimization)
*   **Concept:** RLHF without the heavy reinforcement learning math. It uses the same preference data but is significantly faster and easier to train.
*   **The Impact:** Most modern AI teams are skipping RLHF and moving straight to DPO. It provides 80% of the quality for 20% of the pain.
*   **Use Case:** Rapidly aligning a customer support agent to sound "polite and concise" based on a dataset of good and bad support tickets.

### 4. PEFT (Parameter-Efficient Fine-Tuning)
*   **Concept:** Instead of updating all 70 Billion weights in a model (which requires massive GPU clusters), you freeze the base model and only train small adapter layers.

### 5. LoRA (Low-Rank Adaptation)
*   **Concept:** The PEFT method that won the industry. You inject small, trainable matrices into the frozen layers.
*   **The Impact:** You can fine-tune a 70B model on a single GPU. You merge the weights at the end with zero inference overhead.

### 6. QLoRA (Quantized LoRA)
*   **Concept:** LoRA performed on a 4-bit quantized base model.
*   **The Impact:** Yields the same results as LoRA but uses half the memory. This is how engineers are fine-tuning massive models on a single 24GB consumer graphics card.
*   **Architectural Application:** Building a mobile app with a base Gemma 4 model, and dynamically swapping tiny QLoRA adapters into RAM when the user switches tasks (e.g., from Legal translation to Medical translation).

---
*Tags: #FineTuning #LoRA #QLoRA #DPO #PEFT #LLMTraining*