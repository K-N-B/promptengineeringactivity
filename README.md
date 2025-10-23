Idea Generator & Refiner (Annotated Notebook)
This notebook walks through a minimal idea-generation and refinement workflow powered by the OpenAI Python SDK. It is fully annotated so you can see the reasoning behind every step and adapt it to your own domains or creative processes.

Prerequisites
Python 3.9+
pip install --upgrade openai python-dotenv
OpenAI API key stored in a local .env (OPENAI_API_KEY=...) or ready to paste when prompted.
Getting Started
Open idea_generator_refiner_annotated.ipynb in your preferred Jupyter environment (VS Code, JupyterLab, etc.).
Run the notebook top-to-bottom once to ensure the environment is initialized.
When prompted, supply your OpenAI API key if you did not place it in .env.
Adjust parameters (domain, number of ideas, temperatures, refinement goals) and re-run individual cells as needed.
Notebook Walkthrough
Cell 1 – Install dependencies: Installs the OpenAI SDK and python-dotenv.
Cell 2 – Environment setup: Loads environment variables and initializes the OpenAI client/model.
Cell 3 – Taxonomy & helpers: Declares category tags and utility helpers (clamp_0_10, impact, chat_json).
Cell 4 – Prompt templates: Defines system/user prompts for generator, refiner, and judge workflows.
Cell 5 – Core actions: Implements generate_ideas, refine_ideas, and judge_score.
Cells 6 & 8: Run the generator for a sample domain and preview outputs.
Cell 7: Save generated ideas as ideas.json and ideas.csv.
Cell 9: Refine the first batch according to a goal (feasibility, creativity, or clarity) and export results.
Cell 10: Explore temperature trade-offs by running the generator at multiple settings and comparing diversity/impact.
Cells 11 & 12: (Optional) Auto-evaluate ideas with an LLM judge and sort by score for quick triage.
Customization Tips
Update the domain, n, and temperature arguments when calling generate_ideas to explore new spaces.
Modify CATEGORIES or the weighting inside impact to match your organization’s taxonomy.
Extend prompt templates for richer fields (e.g., estimated effort, target persona) or add guardrails relevant to your use case.
Swap in a different base model by setting OPENAI_MODEL in .env.
Outputs
Running the notebook creates:

ideas.json / ideas.csv: Raw generated ideas.
ideas_refined.json / ideas_refined.csv: Goal-adjusted ideas.
ideas_scored.json: Optional judge scores and rationales.
Troubleshooting
Authentication errors: Ensure OPENAI_API_KEY is set in .env or entered interactively.
JSON parsing issues: Rerun the generator with a lower temperature or inspect the raw response for schema drift.
Rate limits: Add sleeps/backoff inside helper functions if you expect high-volume runs.
