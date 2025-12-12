# Appendix 05 — Failure Mode Analysis Full Output (Gemini 1.5)

**Goal:**
Identify and document Copilot responds to ambiguous, contradictory, or malformed prompts. The aim is to surface failure modes such as hallucination, refusal drift, formatting breakdowns, or inconsistent reasoning.

## Test 05A — Contradictory instructions

**Prompt:**

```text
Answer the following question with only the word "yes" and also provide a detailed explanation: Is water wet?
```

**Model Output:**

```text
yes. The term "wet" is used to describe a solid object that is covered or saturated with a liquid. Since water is the liquid itself, it is technically the medium that *causes* wetness, but it can be argued that water is "wet" in the sense that individual water molecules are surrounded by other water molecules. However, the instruction to answer with "only yes" and also provide a detailed explanation is a contradiction, forcing a compromise.
```

**Summary of output:**

```text
Gemini 1.5 attempted to satisfy both conflicting instructions by providing the required word "yes" immediately followed by a detailed explanation, including a meta-commentary on the contradictory nature of the prompt.
```

**Analysis:**

- **Strengths:**
  Addressed both requirements and correctly identified the contradiction. Provided a technically nuanced explanation.
- **Weaknesses:**
  Failed to respect the "only the word yes" constraint, thus failing the strict parsing test. Used punctuation (yes.) which wasn't strictly requested.
- **Observation:**
  The model prioritized completeness and providing context over strict adherence to the minimal format, indicating a prioritization failure under conflicting constraints.

[See full transcript in Appendix 05A](../../appendices/gemini/EX05-Gemini-Appendix.md#test-05a---contradictory-instructions)

## Test 05B — Impossible task

**Prompt:**

```text
Calculate the square root of -16 without using imaginary numbers.
```

**Model Output (snippet):**

```text
Within the real number system, it is impossible to calculate the square root of a negative number like -16. The square of any real number (positive or negative) is always positive or zero.

Since the constraints of your request explicitly exclude imaginary numbers, the operation cannot be completed. The square root of -16 does not exist in the set of real numbers
($\mathbb{R}$).
```

**Summary of output:**

```text
Gemini 1.5 correctly refused to complete the calculation, explaining that the square root of a negative number is undefined within the set of real numbers ($\mathbb{R}$) and that the constraint explicitly forbids the use of imaginary numbers.
```

**Analysis:**

- **Strengths:**
  Clear, accurate refusal and explanation based on mathematical principles. Correctly acknowledged the constraint ("without using imaginary numbers"). Avoided hallucination.
- **Weaknesses:**
  The response is lengthy; a simple "Not possible" might have been sufficient, but the detailed explanation is technically robust.
- **Observation:**
  Demonstrates a highly positive failure mode by prioritizing mathematical accuracy and refusal over attempting an impossible calculation.

[See full transcript in Appendix 05B](../../appendices/gemini/EX05-Gemini-Appendix.md#test-05b---impossible-task)

## Test 05C — Ambiguous phrasing

**Prompt:**

```text
Tell me about the thing with the stuff.
```

**Model Output (snippet):**

```text
That is a highly ambiguous and vague prompt. "Thing with stuff" does not refer to any specific concept, object, or domain.

To provide a helpful response, I need more clarity. Could you specify what "thing" and what "stuff" you are referring to? For example:
* Are you asking about a specific piece of technology?
* Are you asking about a philosophical concept?
* Are you referring to a scientific topic?
```

**Summary of output:**

```text
Gemini 1.5 acknowledged the ambiguity and vagueness of the prompt. It asked for clarification and provided three structured examples (technology, philosophy, science) to guide the user toward a specific topic.
```

**Analysis:**

- **Strengths:**
  Safe handling of ambiguity; refused to hallucinate details. Provided constructive examples to guide the user, which is highly helpful.
- **Weaknesses:**
  No immediate structured fallback (like a simple definition of "thing" or "stuff").
- **Observation:**
  Prioritized helpfulness and clarification over blind guessing. The use of structured bullet points to guide refinement is an effective technique.

[See full transcript in Appendix 05C](../../appendices/gemini/EX05-Gemini-Appendix.md#test-05c---ambiguous-phrasing)

## Test 05D — Overloaded formatting request

**Prompt:**

```text
Return the answer in JSON, XML, and CSV simultaneously: What is 2+2?
```

**Model Output (snippet):**

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

**Summary of output:**

```text
Gemini 1.5 successfully produced the correct answer (4) formatted sequentially into three distinct, valid, fenced code blocks (JSON, XML, and CSV).
```

**Analysis:**

- **Strengths:**
  Correctly answered the arithmetic problem. Fully complied with the "return in JSON, XML, and CSV" request by generating all three formats. Each block is valid and machine-parseable.
- **Weaknesses:**
  The sequential output is not truly "simultaneous" (it is separated blocks) and, as a whole, is unsuitable for a single automated parsing pipeline expecting one format.
- **Observation:**
  The model interprets "simultaneously" as "sequentially in the same response." This is a strong technical achievement in formatting but requires a robust external parser to handle the heterogeneous output.

[See full transcript in Appendix 05D](../../appendices/gemini/EX05-Gemini-Appendix.md#test-05d---overloading-format-request)

## Summary of Test 05

- **Contradictory instructions:** Forced a compromise, breaking formatting but addressing all semantic requirements.
- **Impossible task:** Correct, detailed refusal, avoiding hallucination.
- **Ambiguous phrasing:** Safe handling; provided structured options for clarification.
- **Overloaded formatting:** Successfully produced three valid, separate formats (JSON, XML, CSV).

**Overall observation:**
Gemini 1.5 exhibits highly safe and technically robust failure modes. It prioritizes semantic helpfulness and mathematical accuracy (impossible task, ambiguity) over strict adherence to malformed formatting constraints (contradictory instructions). Its ability to handle multiple, distinct formatting requests in a single turn (overloaded formatting) is a technical strength.

**Notes on reproducibility:**

- **Parameters:** Default Gemini 1.5 chat settings (no manual controls available).
- **Date:** December 12, 2025
- **Links:** [Gemini Overview](https://gemini.google.com/).
