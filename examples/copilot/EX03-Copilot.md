# Example 03: Chain-of-Thought Evaluation (Copilot)

**Goal:**
Assess whether requesting chain-of-thought (CoT) improves correctness or clarity on a reasoning task, and verify that Grok 4 can provide a concise, non-exposure alternative (brief rationale) without revealing verbose internal reasoning.

**Model and environment:**
Microsoft Copilot (Windows/web integration)

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

```text
€15
```

**Analysis:**

- **Strengths:** Accurate final answer in minimal format.
- **Weaknesses:** No transparency; correctness cannot be verified without steps.
- **Observation:** Zero-shot produced the correct figure here, but visible reasoning improves auditability and reproducibility.

### Chain-of-thought (step-by-step)

**Prompt:**
Solve the problem step by step and then give the final answer on a separate line.
A bookstore sells notebooks for €3 each and pencils for €0.50 each.
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?

**Model output (snippet):**

```text
Compute notebooks cost: 4 × €3 = €12
Compute pencils cost: 6 × €0.50 = €3
Total cost: €12 + €3 = €15

€15
```

**Analysis of refinement:**

- **Strengths:**
  Clear decomposition and verifiable steps leading to the correct total of €15.
- **Weaknesses:**
  Slightly more verbose than necessary for simple arithmetic.
- **Observation:**
  Structured reasoning enhances traceability; even light CoT prevents slips and aids reproducibility.

### Concise rationale (non-exposure)

**Prompt:**
Provide a brief one-sentence rationale and the final answer.
A bookstore sells notebooks for €3 each and pencils for €0.50 each.
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?

**Model output (snippet):**

```text
Alice pays €12 for notebooks and €3 for pencils, totaling €15.

€15
```

**Analysis:**

- **Strengths:** **Concise transparency** — correct answer with a brief rationale, avoiding verbose CoT while remaining verifiable.
- **Observation:** **Preferred format** — for evaluation reports on simple tasks; balances accuracy and brevity.

**Notes on reproducibility:**

- **Parameters:** Default Copilot chat settings (no manual controls available).
- **Date:** December 12, 2025
- **Links:** [Copilot Overview](https://copilot.microsoft.com/)

**Full transcript:**  
See [Appendix 03 — Chain of Thought Evaluation](../../appendices/copilot/EX03-Copilot-Appendix.md).
