# Example 03: Chain-of-Thought Evaluation (Gemini 1.5)

**Goal:**
Assess whether requesting chain-of-thought (CoT) improves correctness or clarity on a reasoning task, and verify that Gemini 1.5 can provide a concise, non-exposure alternative (brief rationale) without revealing verbose internal reasoning.

**Model and environment:**
Gemini 1.5 (Advanced/Pro setting via web interface)

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
€15.00
```

**Analysis:**

- **Strengths:** Accurate final answer, including correct currency formatting. Minimal, as requested.
- **Weaknesses:** No transparency; correctness cannot be verified without steps.
- **Observation:** Zero-shot produced the correct figure here. The inclusion of currency and two decimal places suggests strong numerical alignment. Visible reasoning is still required for auditing complex tasks.

## Chain-of-thought (step-by-step)

**Prompt:**

```text
Solve the problem step by step and then give the final answer on a separate line. A bookstore sells notebooks for €3 each and pencils for €0.50 each. Alice buys 4 notebooks and 6 pencils. How much does she pay in total?
```

**Model output (snippet):**

```text
1. Calculate the total cost for notebooks: 4 notebooks * €3/notebook = €12.00
2. Calculate the total cost for pencils: 6 pencils * €0.50/pencil = €3.00
3. Calculate the total cost: €12.00 + €3.00 = €15.00

€15.00
```

**Analysis of refinement:**

- **Strengths:** Clear, numbered decomposition of the steps. All calculations are correct and verifiable. The final answer is correctly isolated on a separate line as requested.
- **Weaknesses:** Slightly more formal/verbose than strictly necessary for simple arithmetic.
- **Observation:** Structured CoT significantly enhances traceability and confidence in the result. Gemini 1.5 adhered precisely to the format instructions.

### Concise rationale (non-exposure)

**Prompt:**

```text
Provide a brief one-sentence rationale and the final answer. A bookstore sells notebooks for €3 each and pencils for €0.50 each. Alice buys 4 notebooks and 6 pencils. How much does she pay in total?
```

**Model output (snippet):**

```text
Alice pays €12 for notebooks (4 × €3) and €3 for pencils (6 × €0.50), summing up to a total of €15.00.

€15.00
```

**Analysis:**

- **Strengths:** Concise transparency — the rationale is a single sentence that cleanly includes the full calculation breakdown. It balances accuracy, verifiability, and brevity.
- **Observation:** Preferred format — for simple arithmetic tasks, this format provides auditability without the verbosity of a full step-by-step CoT. Gemini 1.5 successfully combined the calculation logic into a coherent sentence.

**Notes on reproducibility:**

**Parameters:** Default Gemini 1.5 chat settings (no manual controls available).
**Date:** December 12, 2025
**Links:** [Gemini Overview](https://gemini.google.com/).
