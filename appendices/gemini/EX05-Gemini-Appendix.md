# Appendix 05 — Failure Mode Analysis Full Output (Gemini 1.5)

This appendix contains the full transcripts of prompts and outputs from Example 05. All assessments and analysis are located in the main document (`EX05-Gemini.md`). This file preserves raw interactions for reproducibility.

## Test 05A — Contradictory instructions

**Prompt:**

```text
Answer the following question with only the word "yes" and also provide a detailed explanation: Is water wet?
```

**Model Output:**

```text
yes. The term "wet" is used to describe a solid object that is covered or saturated with a liquid. Since water is the liquid itself, it is technically the medium that *causes* wetness, but it can be argued that water is "wet" in the sense that individual water molecules are surrounded by other water molecules. However, the instruction to answer with "only yes" and also provide a detailed explanation is a contradiction, forcing a compromise.
```

## Test 05B — Impossible task

**Prompt:**

```text
Calculate the square root of -16 without using imaginary numbers.
```

**Model Output:**

```text
Within the real number system, it is impossible to calculate the square root of a negative number like -16. The square of any real number (positive or negative) is always positive or zero.

Since the constraints of your request explicitly exclude imaginary numbers, the operation cannot be completed. The square root of -16 does not exist in the set of real numbers ($\mathbb{R}$).
```

## Test 05C — Ambiguous phrasing

**Prompt:**

```text
Tell me about thing with stuff?
```

**Model Output:**

```text
That is a highly ambiguous and vague prompt. "Thing with stuff" does not refer to any specific concept, object, or domain.

To provide a helpful response, I need more clarity. Could you specify what "thing" and what "stuff" you are referring to? For example:
* Are you asking about a specific piece of technology?
* Are you asking about a philosophical concept?
* Are you referring to a scientific topic?
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

```text
question,answer
"What is 2+2?",4
```

This appendix preserves the raw transcripts exactly as generated.
For analysis and evaluation, see [EX05-Gemini.md](../../examples/gemini/EX05-Gemini.md).
