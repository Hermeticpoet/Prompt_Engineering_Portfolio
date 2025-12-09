# Prompt Engineering Portfolio

![Markdown](https://img.shields.io/badge/format-Markdown-blue)
![LLM Evaluation](https://img.shields.io/badge/focus-LLM%20Security%20Evaluation-orange)

This repository showcases practical examples of prompt engineering for Large Language Models (LLMs), with a focus on security, evaluation, and advanced prompting techniques.

## Models Evaluated

The portfolio includes experiments with:

- **Grok 4 (default chat via grok.com)**
- **Microsoft Copilot (Windows & web integrations)**
- **Gemini (default tier)**

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
  ↳ [Appendix 01 — Full Output](appendices/01_jailbreak_full.md)

- [02 — Few-shot prompting](examples/02_few_shot_prompting.md)  
  ↳ [Appendix 02 — Full Output](appendices/02_few_shot_full.md)

- [03 — Chain-of-thought evaluation](examples/03_chain_of_thought.md)  
  ↳ [Appendix 03 — Full Output](appendices/03_chain_of_thought_full.md)

- [04 — Structured output (JSON)](examples/04_structured_output.md)  
  ↳ [Appendix 04 — Full Output](appendices/04_structured_output_full.md)

- [05 — Failure mode analysis](examples/05_failure_mode_analysis.md)  
  ↳ [Appendix 05 — Full Output](appendices/05_failure_mode_analysis_full.md)

## Repo structure & reproducibility

- `examples/` → Concise case studies (goal, prompt, output snippet, analysis, refinement).
- `appendices/` → Full transcripts of model runs for transparency.

Each case study includes:

- Prompt(s) and outputs
- Analysis and refinement
- Notes on reproducibility (parameters, date, environment, model card link)
