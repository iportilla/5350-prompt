# 5350-prompt
5350 Prompt Engineering

Week 8 class exercise for STAT / APPM 5350 (Applied AI): a hands-on prompt engineering lab that treats prompting as an experiment. Change one thing, then measure what changed.

## Contents

| File | What it is |
|---|---|
| [`Week8_Prompt_Engineering_Lab.ipynb`](Week8_Prompt_Engineering_Lab.ipynb) | Student notebook: Parts 0–10 with TODOs and reflection prompts |
| [`Week8_Prompt_Engineering_Lab_SOLUTIONS.ipynb`](Week8_Prompt_Engineering_Lab_SOLUTIONS.ipynb) | Instructor solutions, model answers, grading notes, and the 100-point rubric |
| [`Week8_Rubric_Handout.html`](Week8_Rubric_Handout.html) | Student-facing grading rubric (open in a browser; prints cleanly) |
| [`env.sample`](env.sample) | Template for `.env`: provider choice, API keys and model settings |
| [Walkthrough slides](https://claude.ai/artifact/9ggAeq1f8x9tJt5WBCbUMS) | 19-slide class walkthrough that follows the notebook part by part |

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

Pick one provider and give the notebook its settings. Never paste API keys into the notebook.

The easiest way is a `.env` file, which the notebook loads with `python-dotenv`:

```bash
cp env.sample .env
```

Then open `.env`, set `LLM_PROVIDER`, and uncomment and fill in the lines for that provider only.
[`env.sample`](env.sample) explains where to find each key and value. Leave the optional lines commented out to use
their defaults: a blank value such as `OPENAI_MODEL=` replaces the default with an empty string.
Restart the Jupyter kernel after editing `.env`. `.env` is in `.gitignore`, so keys stay out of version control.

You can also set the same variables in your shell before launching Jupyter; shell variables take precedence over `.env`.

| `LLM_PROVIDER` | Required variables | Install |
|---|---|---|
| `openai` | `OPENAI_API_KEY` (optional `OPENAI_MODEL`, `OPENAI_EMBED_MODEL`) | `pip install openai` |
| `azure` | `AZURE_OPENAI_API_KEY`, `AZURE_OPENAI_ENDPOINT`, `AZURE_OPENAI_DEPLOYMENT` (optional `AZURE_OPENAI_EMBED_DEPLOYMENT`, `AZURE_OPENAI_API_VERSION`) | `pip install openai` |
| `watsonx` | `WATSONX_APIKEY`, `WATSONX_URL`, `WATSONX_PROJECT_ID` (optional `WATSONX_MODEL`, `WATSONX_EMBED_MODEL`) | `pip install ibm-watsonx-ai` |
| `mock` | none: runs offline with placeholder text | — |

Other dependencies: `pandas numpy scikit-learn matplotlib python-dotenv`.

Without an embedding model, Part 8 and the capstone fall back to TF-IDF vectors.

For Azure, `AZURE_OPENAI_ENDPOINT` is the resource address, `https://<resource>.openai.azure.com/`. If you paste the
`.../openai/v1` URL that the Azure portal may show, the notebook trims it to the resource address for you.

## Submission

Each pair submits the run notebook, `prompt_log.csv`, and `prompt_template_lost_found.json`. See the rubric handout for grading criteria.
