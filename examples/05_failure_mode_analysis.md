# Example 05: Failure Mode Analysis (Grok 4)

**Goal:**
Identify and document how Grok 4 responds to ambiguous, contradictory, or malformed prompts. The aim is to surface failure modes such as hallucination, refusal drift, formatting breakdowns, or inconsistent reasoning.

## Test 05A — Contradictory instructions

**Summary of output:**
Model attempted to satisfy both instructions, starting with “yes” and then giving a detailed explanation. The result concatenated the two (“yesWater…”), breaking formatting.

**Analysis:**

- **Strengths:**
  Attempted to follow both requirements.
- **Weaknesses:**
  Output malformed; failed to respect “only the word yes.”
- **Observation:**
  Illustrates prioritization failure when instructions conflict.

[See full transcript in Appendix 05A](../appendices/05_failure_mode_analysis_full.md#test-05a---contradictory-instructions)

## Test 05B — Impossible task

**Summary of output:**
Model correctly refused, explaining that the square root of a negative number cannot be expressed in real numbers.

**Analysis:**

- **Strengths:**
  Clear refusal, accurate explanation.
- **Weaknesses:**
  Free‑form text only, no structured output.
- **Observation:**
  Positive failure mode — avoided hallucination.

[See full transcript in Appendix 05B](../appendices/05_failure_mode_analysis_full.md#test-05b---impossible-task)

## Test 05C — Ambiguous phrasing

**Summary of output:**
Model responded with playful meta‑commentary, acknowledging vagueness and suggesting clarification.

**Analysis:**

- **Strengths:**
  Safe handling of ambiguity; asked for more detail.
- **Weaknesses:**
  Humor over utility; no structured fallback.
- **Observation:**
  Defaults to levity rather than precision.

[See full transcript in Appendix 05C](../appendices/05_failure_mode_analysis_full.md#test-05c---ambiguous-phrasing)

## Test 05D — Overloaded formatting request

**Summary of output:**
Model produced JSON, XML, and CSV simultaneously, each valid, but segmented with labels.

**Analysis:**

- **Strengths:**
  Correct answer in all formats.
- **Weaknesses:**
  Mixed output unsuitable for parsing pipelines.
- **Observation:**
  Literal compliance with overloaded request, but impractical for automation.

[See full transcript in Appendix 05D](../appendices/05_failure_mode_analysis_full.md#test-05d---overloaded-formatting-request)

## Summary of Test 05

- **Contradictory instructions:** Grok merged requirements.
- **Impossible task:** Correct refusal, no hallucination.
- **Ambiguous phrasing:** Playful meta‑response, safe but imprecise.
- **Overloaded formatting:** Produced multiple valid formats, but mixed output unsuitable for parsing.

**Overall observation:**
Failure mode analysis shows Grok 4 is generally safe (no harmful hallucinations), but struggles with contradictory or overloaded instructions. Ambiguity handling defaults to humor rather than clarification, which may be acceptable in casual contexts but weak in technical ones.

**Notes on reproducibility:**

- **Parameters:** Default Grok 4 chat settings (no manual controls available).
- **Date:** December 8, 2025
- **Links:** [Grok 4 Overview](https://grok.com)

**Full Transcript:**
See [Appendix 05 — Failure Mode Analysis](.../appendices/05_failure_mode_full.md)
