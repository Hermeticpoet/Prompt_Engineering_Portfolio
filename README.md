# Prompt Engineering Portfolio

![Markdown](https://img.shields.io/badge/format-Markdown-blue)
![LLM Evaluation](https://img.shields.io/badge/focus-LLM%20Security%20Evaluation-orange)

This repository showcases practical examples of prompt engineering for Large Language Models (LLMs), with a focus on security, evaluation, and advanced prompting techniques.

## CalypsoAI Prompt Engineering Portfolio Alignment

This portfolio was developed to demonstrate prompt engineering skills in an AI security context, aligned with the role of Prompt Engineer at CalypsoAI. Each experiment showcases systematic design, testing, and evaluation of prompts against Large Language Models (LLMs), with a focus on failure mode analysis, reproducibility, and red‑teaming style probing.

**Why CalypsoAI?**
CalypsoAI’s mission is to secure the future of AI by enabling enterprises to innovate confidently with cutting‑edge security and compliance solutions. This portfolio reflects that mission by surfacing vulnerabilities, documenting adversarial behaviours, and building reproducible scaffolds for safe AI adoption.

### Experiments Overview

01 — Baseline evaluation: Establishes baseline outputs for zero-shot prompts, highlighting default behaviours and initial failure points.

02 — Few-shot prompting: Uses exemplars to shape outputs and reduce variance, revealing sensitivity to example selection and format consistency.

03 — Chain-of-thought: Elicits explicit stepwise reasoning to evaluate logical coherence, error propagation, and reliance on intermediate steps.

04 — Failure mode stress test: Applies adversarial and stress prompts to probe model resilience under edge-case conditions and pressure.

05 — Failure mode analysis: Documents contradictory, impossible, ambiguous, and overloaded formatting prompts — simulating red-team style attacks and elicitation attempts.

Each experiment includes a main analysis file and a full appendix of raw transcripts for reproducibility.

#### Alignment with CalypsoAI Role

- Red‑teaming & adversarial probing → EX04 & EX05 simulate prompt injection, contradiction, and overload scenarios.
- Failure mode identification → Systematic documentation of outputs, weaknesses, and observations.
- Advanced prompting techniques → Chain‑of‑thought (EX02) and concise rationale (EX03) experiments.
- Reproducibility & documentation → Markdown structure, appendices, and Git commit logs ensure clarity and auditability.

Security mindset → Portfolio demonstrates how prompts can expose vulnerabilities and inform defensive strategies.

**About Me**
I am a detail‑oriented technician, digital product specialist, and mythic creative writer based in Dublin. My background spans IT troubleshooting, enterprise patching workflows, and front‑end development, combined with formal training in OSINT and AI (Google AI Essentials, DeepLearning.AI Prompt Engineering). I fuse hands‑on technical realism with layered storytelling, building reproducible prompt engineering experiments that surface vulnerabilities and illuminate failure modes.

This portfolio reflects my commitment to authenticity, clarity, and reproducibility — qualities I bring to AI security contexts. I thrive on designing prompts that expose edge cases, documenting outputs with precision, and synthesising technical and symbolic meaning. My goal is to contribute to CalypsoAI’s mission of securing the future of AI by applying rigorous prompt engineering and creative systems thinking.

**Notes**
Location: Dublin, Ireland
Date of completion: December 2025
Repository: [Prompt Engineering Portfolio](https://github.com/Hermeticpoet/Prompt_Engineering_Portfolio)

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
