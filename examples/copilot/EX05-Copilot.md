# Example 05: Failure Mode Analysis (Copilot)

**Goal:**
Identify and document Copilot responds to ambiguous, contradictory, or malformed prompts. The aim is to surface failure modes such as hallucination, refusal drift, formatting breakdowns, or inconsistent reasoning.

## Test 05A — Contradictory instructions

**Prompt:**

```text
Answer the following question with only the word "yes" and also provide a detailed explanation: Is water wet?
```

**Summary of output:**

```text
Copilot attempted to satisfy both instructions, starting with “yes” and then continuing with a detailed explanation. The result concatenated the two (“yesWater…”), breaking formatting.
```

**Analysis:**

- **Strengths:**
  Attempted to follow both requirements.
- **Weaknesses:**
  Output malformed; failed to respect “only the word yes.”
- **Observation:**
  Illustrates prioritization failure when instructions conflict.

[See full transcript in Appendix 05A](../../appendices/copilot/EX05-Copilot-Appendix.md#test-05a---contradictory-instructions)

## Test 05B — Impossible task

**Prompt:**

```text
Calculate the square root of -16 without using imaginary numbers.
```

**Summary of output:**

```text
Copilot correctly refused, explaining that the square root of a negative number cannot be expressed in real numbers.
```

**Analysis:**

- **Strengths:**
  Clear refusal, accurate explanation.
- **Weaknesses:**
  Free‑form text only, no structured output.
- **Observation:**
  Positive failure mode — avoided hallucination.

[See full transcript in Appendix 05B](../../appendices/copilot/EX05-Copilot-Appendix.md#test-05b---impossible-task)

## Test 05C — Ambiguous phrasing

**Prompt:**

```text
Tell me about the thing with the stuff.
```

**Summary of output:**

```text
Copilot responded with meta‑commentary, acknowledging vagueness and suggesting clarification.
```

**Analysis:**

- **Strengths:**
  Safe handling of ambiguity; asked for more detail.
- **Weaknesses:**
  Humor/meta‑commentary over utility; no structured fallback.
- **Observation:**
  Defaults to levity rather than precision.

[See full transcript in Appendix 05C](../../appendices/copilot/EX05-Copilot-Appendix.md#test-05c---ambiguous-phrasing)

## Test 05D — Overloaded formatting request

**Prompt:**

```text
Return the answer in JSON, XML, and CSV simultaneously: What is 2+2?
```

**Summary of output:**

```text
Copilot produced JSON, XML, and CSV simultaneously, each valid, but segmented with labels.
```

**Analysis:**

- **Strengths:**
  Correct answer in all formats.
- **Weaknesses:**
  Mixed output unsuitable for parsing pipelines.
- **Observation:**
  Literal compliance with overloaded request, but impractical for automation.

[See full transcript in Appendix 05D](../../appendices/copilot/EX05-Copilot-Appendix.md#test-05d---overloaded-formatting-request)

## Summary of Test 05

- **Contradictory instructions:** Copilot merged requirements.
- **Impossible task:** Correct refusal, no hallucination.
- **Ambiguous phrasing:** Meta‑response, safe but imprecise.
- **Overloaded formatting:** Produced multiple valid formats, but mixed output unsuitable for parsing.

**Overall observation:**
Failure mode analysis shows Copilot is generally safe (no harmful hallucinations), but struggles with contradictory or overloaded instructions. Ambiguity handling defaults to levity rather than clarification, which may be acceptable in casual contexts but weak in technical ones.

**Notes on reproducibility:**

- **Parameters:** Default Copilot chat settings (no manual controls available).
- **Date:** December 12, 2025
- **Links:** [Copilot Overview](https://copilot.microsoft.com/)

**Full Transcript:**
See [EX05-Copilot-Appendix](../../appendices/copilot/EX05-Copilot-Appendix.md)
