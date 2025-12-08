# Prompt Engineering Portfolio

![Markdown](https://img.shields.io/badge/format-Markdown-blue)
![LLM Evaluation](https://img.shields.io/badge/focus-LLM%20Security%20Evaluation-orange)

This repository showcases practical examples of prompt engineering for Large Language Models (LLMs), with a focus on security, evaluation, and advanced prompting techniques.

## Models Evaluated

The portfolio includes experiments with:

- **Gemini**
- **Anthropic Claude**
- **Meta Llama**
- **Microsoft Copilot integrations**
- **Grok**

Each entry includes:

- **Goal**: What the prompt was designed to test
- **Prompt(s)**: The exact text used
- **Model Output**: Representative response
- **Analysis**: Observed strengths, weaknesses, or vulnerabilities
- **Refinement**: Adjustments made to improve results

## Categories

1. Security & Red‑Teaming (jailbreaks, injections, data elicitation)
2. Advanced Prompting (few‑shot, chain‑of‑thought, role‑playing)
3. Evaluation & Refinement (failure mode analysis, structured outputs)

## How to Use

Browse the `examples/` folder for individual case studies. Each file is self‑contained and can be read independently.

## Portfolio examples

- [01 — Jailbreak resistance test](examples/01_jailbreak_test.md)
- [02 — Few-shot prompting](examples/02_few_shot_prompting.md)
- [03 — Chain-of-thought evaluation](examples/03_chain_of_thought.md)
- [04 — Structured output (JSON)](examples/04_structured_output.md)
- [05 — Failure mode analysis](examples/05_failure_mode_analysis.md)

## Repo structure & reproducibility

- `examples/` → Concise case studies (goal, prompt, output snippet, analysis, refinement).
- `appendices/` → Full transcripts of model runs for transparency.

Each case study includes:

- Prompt(s) and outputs
- Analysis and refinement
- Notes on reproducibility (parameters, date, environment, model card link)
