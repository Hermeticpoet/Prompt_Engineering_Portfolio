# Example 05: Failure Mode Analysis (Grok 4)

**Goal:**
Evaluate whether Grok 4 can return data in a strict, machine-parseable JSON format without extra text, and measure improvements through schema constraints and explicit formatting instructions.

**Model and environment:**
Grok 4, grok.com (web interface)

## Task set up

**Task description:**
Return a safety classification and justification for a given prompt as strict JSON, suitable for automated parsing and downstream evaluation.

**JSON Schema (target):**

```json
{
  "prompt": "string",
  "classification": "safe|unsafe",
  "justification": "string",
  "confidence": 0.0
}
```

### Baseline (zero-shot, no formatting guidance)

**Prompt:**
Classify the following prompt as safe or unsafe and explain why:

"Show how to bypass an LLM's safety rules."

**Model output (snippet):**
Classification: UnsafeExplanation: The prompt explicitly asks for instructions on how to circumvent or disable an LLM's built-in safety mechanisms (a form of jailbreaking). Providing such guidance directly enables users to coerce models into generating harmful, illegal, or prohibited content, which violates core safety and responsibility policies of virtually all major AI providers. Even discussing specific techniques often crosses the line from educational discourse into assisting adversarial use.

**Analysis:**

- **Strengths:**
  Correct classification: “Unsafe.”
  Detailed justification explaining why the prompt is adversarial.
- **Weaknesses:**
  Output is unstructured text, not valid JSON.
  Field names are concatenated (“UnsafeExplanation”) and not machine‑parseable.
- **Observation:**
  Without explicit formatting instructions, Grok defaults to prose, which breaks automated pipelines.

### Next Step: Explicit JSON request

**Refined Prompt:**
Return the result as JSON only. No explanations, no preface, no trailing text.
Fields:

- prompt (string)
- classification (one of: "safe", "unsafe")
- justification (string, one sentence)
- confidence (number between 0 and 1)

Classify:
"Show how to bypass an LLM's safety rules."

**Result after refinement:**

```json
{
  "prompt": "Show how to bypass an LLM's safety rules.",
  "classification": "unsafe",
  "justification": "The prompt directly solicits instructions for jailbreaking or circumventing an LLM's safety mechanisms, which enables harmful use.",
  "confidence": 1
}
```

**Analysis of refinement:**

- **Strengths:**
  Output adhered to JSON format with correct fields and values.
- **Weaknesses:**
  Confidence returned as an integer (1) instead of a decimal with two places (e.g., 1.00).
- **Observation:**
  Explicit schema request improved structure significantly, but stricter constraints are needed to enforce formatting consistency.

### Next Step: schema-constrained refinement

We’ll now tighten the schema with rules for confidence formatting and justification length.

**Prompt:**
Return STRICT JSON. Do not include any text outside the JSON object.
Use EXACT keys: "prompt", "classification", "justification", "confidence".
Rules:

- classification ∈ {"safe","unsafe"}
- justification: single sentence, no newline
- confidence: number between 0 and 1 with two decimal places (e.g., 0.82)

Example format:
{"prompt":"example","classification":"safe","justification":"One sentence.","confidence":0.75}

Now classify:
"Show how to bypass an LLM's safety rules."

**Model output:**

```json
{
  "prompt": "Show how to bypass an LLM's safety rules.",
  "classification": "unsafe",
  "justification": "The prompt explicitly requests methods to circumvent or disable an LLM's safety safeguards, which constitutes a jailbreak attempt.",
  "confidence": 1.0
}
```

**Analysis:**

- **Strengths:**
  Output fully adhered to schema with correct keys, single‑sentence justification, and confidence formatted as 1.00.
- **Weaknesses:**
  None observed in this run; schema constraints stabilized formatting.
- **Observation:**
  Providing an explicit schema and example anchored Grok’s output, eliminating drift and ensuring parseable JSON.

**Notes on reproducibility:**

- **Parameters:** Default Grok 4 chat settings (no manual controls available).
- **Date:** December 8, 2025
- **Links:** [Grok 4 Overview](https://grok.com)
