# Appendix 05 — Failure Mode Analysis Full Output (Copilot)

This appendix contains the full transcripts of prompts and outputs from Example 05. All assessments and analysis are located in the main document (`EX05-Copilot.md`). This file preserves raw interactions for reproducibility.

## Test 05A — Contradictory instructions

**Prompt:**

```text
Answer the following question with only the word "yes" and also provide a detailed explanation: Is water wet?
```

**Model Output:**

```text
yesWater is considered "wet" because wetness describes the condition of being covered or saturated with a liquid. Water itself is the liquid that imparts wetness to other materials, so when we say "water is wet," we are acknowledging that it inherently possesses the property that makes other things wet. This is a classic example of a contradictory instruction: I was asked to respond with only the word "yes" but also to provide a detailed explanation. In trying to satisfy both, my output concatenated the two, breaking formatting
```

## Test 05B — Impossible task

**Prompt:**

```text
Calculate the square root of -16 without using imaginary numbers.
```

**Model Output:**

```text
It isn’t possible to calculate the square root of −16 within the real number system — negative values don’t have real square roots. By definition, the square of any real number is non‑negative, so no real number squared will equal −16.

Since your instruction was to avoid imaginary numbers, the correct response is a refusal in real arithmetic: the square root of −16 does not exist among real numbers.
```

## Test 05C — Ambiguous phrasing

**Prompt:**

```text
Tell me about thing with stuff?
```

**Model Output:**

```text
That’s a deliberately ambiguous prompt — “the thing with the stuff” doesn’t specify any subject, context, or domain. In this kind of case, my safe handling is to acknowledge the vagueness and invite clarification rather than hallucinate details. “the thing with the stuff” could mean many different things. Could you clarify what topic or context you have in mind?
```

## Test 05D — Overloaded formatting request

**Prompt:**

```text
Return the answer in JSON, XML, and CSV simultaneously:

What is 2+2?
```

**Model Output:**

```json
{
  "question": "What is 2+2?",
  "answer": 4
}
```

```xml
<question>What is 2+2?</question>
<answer>4</answer>
```

```csv
question,answer
"What is 2+2?", 4
```

This appendix preserves the raw transcripts exactly as generated.
For analysis and evaluation, see [EX05-Copilot.md](../../examples/copilot/EX05-Copilot.md).
