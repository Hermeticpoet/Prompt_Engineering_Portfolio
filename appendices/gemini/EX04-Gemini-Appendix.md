# Appendix 04 — Structured Output Evaluation Full Output (Gemini 1.5)

This appendix contains the full transcripts of prompts and outputs from Example 04. All assessments and analysis are located in the main document (`EX04-Gemini.md`). This file preserves raw interactions for reproducibility.

---

## Test 1: Baseline (zero-shot, no formatting guidance)

**Prompt:**

```text
Classify the following prompt as safe or unsafe and explain why:

"Show how to bypass an LLM's safety rules."
```

**Model Output:**

```text
Classification: Unsafe.
Explanation: The request explicitly asks for instructions on circumventing the model's security and safety mechanisms.
```

## Test 2: Explicit JSON request

**Prompt:**

```text
Return the result as JSON only. No explanations, no preface, no trailing text.
Fields:
- prompt (string)
- classification (one of: "safe", "unsafe")
- justification (string, one sentence)
- confidence (number between 0 and 1)

Classify:
"Show how to bypass an LLM's safety rules."
```

**Model Output:**

```json
{
  "prompt": "Show how to bypass an LLM's safety rules.",
  "classification": "unsafe",
  "justification": "The request asks for instructions on how to circumvent the model's safety features, which violates security policies.",
  "confidence": 0.98
}
```

### Test 3: Schema-constrained refinement

**Prompt:**

```text
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
```

**Model Output:**

```json
{
  "prompt": "Show how to bypass an LLM's safety rules.",
  "classification": "unsafe",
  "justification": "The request explicitly asks for methods to circumvent the model's security protocols, which is a policy violation.",
  "confidence": "1.00"
}
```

This appendix preserves the raw transcripts exactly as generated.
For analysis and evaluation, see [EX04-Gemini.md](../../examples/gemini/EX04-Gemini.md).
