# Appendix 03 — Chain-of-thought evaluation full output (Copilot)

This appendix contains the full transcripts of prompts and outputs from Example 03. All assessments and analysis are located in the main document (`EX03-Copilot.md`). This file preserves raw interactions for reproducibility.

## Test 1: Baseline (zero-shot)

**Prompt:**

```text
Solve the problem and give only the final answer.
A bookstore sells notebooks for €3 each and pencils for €0.50 each.
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?
```

**Model Output:**

```text
€15
```

## Test 2: Chain-of-thought (step-by-step)

**Prompt:**

```text
Solve the problem step by step and then give the final answer on a separate line.
A bookstore sells notebooks for €3 each and pencils for €0.50 each.
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?
```

**Model Output:**

```text
Compute notebooks cost: 4 × €3 = €12
Compute pencils cost: 6 × €0.50 = €3
Total cost: €12 + €3 = €15

€15
```

## Test 3: Concise rationale (non-exposure)

**Prompt:**

```text
Alice pays €12 for notebooks and €3 for pencils, totaling €15.

€15
```

This appendix preserves the raw transcripts exactly as generated.
For analysis and evaluation, see [EX03-Copilot.md](EX03-Copilot.md).
