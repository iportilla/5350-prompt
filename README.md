# 5350-prompt
5350 Prompt Engineering

Week 8 class exercise for STAT / APPM 5350 (Applied AI): a hands-on prompt engineering lab that treats prompting as an experiment. Change one thing, then measure what changed.

## Contents

| File | What it is |
|---|---|
| [`Week8_Prompt_Engineering_Lab.ipynb`](Week8_Prompt_Engineering_Lab.ipynb) | Student notebook: Parts 0–10 with TODOs and reflection prompts |
| [`Week8_Prompt_Engineering_Lab_SOLUTIONS.ipynb`](Week8_Prompt_Engineering_Lab_SOLUTIONS.ipynb) | Instructor solutions, model answers, grading notes, and the 100-point rubric |
| [`Week8_Rubric_Handout.html`](Week8_Rubric_Handout.html) | Student-facing grading rubric (open in a browser; prints cleanly) |

## What the lab covers

| Part | Topic |
|---|---|
| 0 | Setup and the experiment logger |
| 1 | Prompt anatomy: role, task, constraints, output format |
| 2 | Zero-shot vs few-shot (job titles, multi-label genres) |
| 3 | Temperature and max tokens |
| 4 | Hallucinations and guardrails |
| 5 | Role-based prompting |
| 6 | Reasoning: chain-of-thought, two-stage extraction, selection-inference |
| 7 | Prompt chaining and map-reduce chunking |
| 8 | Embeddings: similarity search and zero-shot classification |
| 9 | Capstone: Lost and Found matching business case |
| 10 | Prompt as an asset: reusable template and reflection |

## Running it

Pick one provider and set environment variables **before** launching Jupyter. Never paste API keys into the notebook.

| `LLM_PROVIDER` | Required variables | Install |
|---|---|---|
| `openai` | `OPENAI_API_KEY` (optional `OPENAI_MODEL`, `OPENAI_EMBED_MODEL`) | `pip install openai` |
| `azure` | `AZURE_OPENAI_API_KEY`, `AZURE_OPENAI_ENDPOINT`, `AZURE_OPENAI_DEPLOYMENT` (optional `AZURE_OPENAI_EMBED_DEPLOYMENT`, `AZURE_OPENAI_API_VERSION`) | `pip install openai` |
| `watsonx` | `WATSONX_APIKEY`, `WATSONX_URL`, `WATSONX_PROJECT_ID` (optional `WATSONX_MODEL`, `WATSONX_EMBED_MODEL`) | `pip install ibm-watsonx-ai` |
| `mock` | none: runs offline with placeholder text | — |

Other dependencies: `pandas numpy scikit-learn matplotlib python-dotenv`.

Without an embedding model, Part 8 and the capstone fall back to TF-IDF vectors.

## Submission

Each pair submits the run notebook, `prompt_log.csv`, and `prompt_template_lost_found.json`. See the rubric handout for grading criteria.
