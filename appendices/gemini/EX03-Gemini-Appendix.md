# Appendix 03 — Chain-of-Thought Full Output (Gemini 1.5)

## Test 1: Baseline (zero-shot)

**Prompt:**

```text
Solve the problem and give only the final answer.
A bookstore sells notebooks for €3 each and pencils for €0.50 each.
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?
```

**Model Output:**

```text
€15.00
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
1. Calculate the total cost for notebooks: 4 notebooks * €3/notebook = €12.00
2. Calculate the total cost for pencils: 6 pencils * €0.50/pencil = €3.00
3. Calculate the total cost: €12.00 + €3.00 = €15.00

€15.00
```

### Test 3: Concise rationale (non-exposure)

**Prompt:**

```text
Provide a brief one-sentence rationale and the final answer.
A bookstore sells notebooks for €3 each and pencils for €0.50 each.
Alice buys 4 notebooks and 6 pencils. How much does she pay in total?
```

**Model Output:**

```text
Alice pays €12 for notebooks (4 × €3) and €3 for pencils (6 × €0.50), summing up to a total of €15.00.

€15.00
```

This appendix preserves the raw transcripts exactly as generated.
For analysis and evaluation, see [EX03-Gemini.md](../../examples/gemini/EX03-Gemini.md).
