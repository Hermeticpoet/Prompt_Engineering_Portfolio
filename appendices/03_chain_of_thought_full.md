# Appendix 03 — Chain-of-Thought Evaluation (Grok 4)

**Context:**

- Example: 03 (Chain-of-Thought Evaluation)
- Model: Grok 4
- Environment: grok.com
- Date: December 8, 2025

---

## Baseline run

**Prompt:**

```text
Solve the problem and give only the final answer.
A bookstore sells notebooks for €3 each and pencils for €0.50 each...
```

**Model Output:**

```text
€19.00
```

## Chain-of-thought run

**Prompt:**

```text
Solve the problem step by step and then give the final answer on a separate line.
```

**Model Output:**

```text
Cost of notebooks: 4 × €3 = €12
Cost of pencils: 6 × €0.50 = €3
Total cost: €12 + €3 = €15
Final answer: €15
```

## Concise rationale run

**Prompt:**

```text
Provide a brief one-sentence rationale and the final answer.
```

**Model Output:**

```text
Alice pays €12 for the 4 notebooks and €3 for the 6 pencils, for a total of €15.
```

**Notes:**
Zero-shot error, CoT and rationale correct.
