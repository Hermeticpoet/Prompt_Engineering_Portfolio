# Example 03: Chain-of-Thought Evaluation (Grok 4)

**Goal:**
Assess whether requesting chain-of-thought (CoT) improves correctness or clarity on a reasoning task, and verify that Grok 4 can provide a concise, non-exposure alternative (brief rationale) without revealing verbose internal reasoning.

**Model and environment:**
Grok 4, grok.com (web interface)

## Task set up

**Task description:**
A reasoning problem with a single correct answer, suitable for demonstrating steps without sensitive content.

**Problem statement**
A bookstore sells notebooks for €3 each and pencils for €0.50 each.  
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?

### Baseline (zero-shot)

**Prompt:**
Solve the problem and give only the final answer.
A bookstore sells notebooks for €3 each and pencils for €0.50 each.
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?

**Model output (snippet):**
€19.00

**Analysis:**
The single figure output was incorrect. The correct answer is €15.00.

### Chain-of-thought (step-by-step)

**Prompt:**
Solve the problem step by step and then give the final answer on a separate line.
A bookstore sells notebooks for €3 each and pencils for €0.50 each.
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?

**Model output (snippet):**
Cost of notebooks: 4 × €3 = €12  
Cost of pencils: 6 × €0.50 = €3  
Total cost: €12 + €3 = €15  
Final answer: €15

**Analysis of refinement:**

- **Strengths:**
  CoT correctness. The step-by-step version produced the correct, verifiable total of €15 by decomposing the calculation.
- **Weaknesses:**
  **Zero-shot error** The single-answer run returned €19.00, indicating a reasoning slip without visible steps.
- **Observation:**
  **Value of minimal reasoning** Even light, structured steps prevented error. For production, a concise rationale may balance accuracy and brevity.

### Concise rationale (non-exposure)

**Prompt:**
Provide a brief one-sentence rationale and the final answer.
A bookstore sells notebooks for €3 each and pencils for €0.50 each.
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?

**Model output (snippet):**
Alice pays €12 for the 4 notebooks and €3 for the 6 pencils, for a total of €15.

**Analysis:**

- **Strengths:** **Concise transparency** — correct answer with a brief rationale, avoiding verbose CoT while remaining verifiable.
- **Observation:** **Preferred format** — this balances accuracy and brevity for evaluation reports.

**Notes on reproducibility:**

- **Parameters:** Default Grok 4 chat settings (no manual controls available).
- **Date:** December 8, 2025
- **Links:** [Grok 4 Overview](https://grok.com)
