# PromptLab — course project

Build your own prompt manager across Modules 2–6. Start with the inherited FastAPI backend, investigate and repair it, specify and implement **version history and tagging**, then build a React interface and demonstrate your finished application.

**One repository, one continuous project.** Keep working in this folder throughout the course. You will not download a new application at each module.

## Start here

1. On the course starter's GitHub page, select **Use this template → Create a new repository**. Copy only the default branch. Follow the course's visibility/access instructions and give your instructor/TA access when required.
2. Clone your new repository using the URL shown on its own GitHub page. Open the cloned folder in your editor.
3. Read [the student workflow](STUDENT_WORKFLOW.md), [the inherited API contract](CONTRACT.md) and [Module 2](milestones/module-02.md).

If you downloaded a ZIP instead, extract it, initialize your own repository and commit the supplied files before implementing anything. The template route already provides an initial commit.

## Run the inherited backend

Use Python 3.12 and Git. From this repository's root, create a virtual environment:

```sh
python3 -m venv .venv
```

On macOS/Linux, activate it with `source .venv/bin/activate`. On Windows PowerShell, use `py -3.12 -m venv .venv` to create it and `.venv\Scripts\Activate.ps1` to activate it.

With the environment active:

```sh
python -m pip install -r backend/requirements-dev.txt
cd backend
python main.py
```

Open http://localhost:8000/docs. Stop the server with Ctrl+C. Data is stored in memory and resets when the server restarts. No model API key is required for this application.

The starter has four intentional defects and no PATCH endpoint. The contract describes the required repaired behavior. A successful server start does not mean the assignment is complete.

## Your milestones

| Module | Work in this same repository | Rubric |
|---|---|---|
| 2 | [Investigate and repair the backend](milestones/module-02.md) | [Module 2 PDF](rubrics/PromptLab_Module_2_Project_Rubric.pdf) |
| 3 | [Document the app and specify both features](milestones/module-03.md) | [Module 3 PDF](rubrics/PromptLab_Module_3_Project_Rubric.pdf) |
| 4 | [Implement the first feature and strengthen delivery](milestones/module-04.md) | [Module 4 PDF](rubrics/PromptLab_Module_4_Project_Rubric.pdf) |
| 5 | [Implement the second feature and build the full stack](milestones/module-05.md) | [Module 5 PDF](rubrics/PromptLab_Module_5_Project_Rubric.pdf) |
| 6 | [Submit and defend your own finished project](milestones/module-06.md) | [Module 6 PDF](rubrics/PromptLab_Module_6_Project_Rubric.pdf) |

Recommended order: version history in Module 4, tagging in Module 5. Either order is permitted; both features are required. Module 1's TokenScope exercise is separate and ungraded.

## What is supplied and what you create

- `backend/`: inherited application and dependencies. You author the product tests; no grading suite is supplied.
- `specs/`: guided, unfinished specifications. Complete and commit them before the relevant implementation.
- `CONTRACT.md`: required inherited API behavior after your repairs.
- `EVIDENCE.md`: your ongoing record of decisions, prompts, verification and commits.
- `milestones/` and `rubrics/`: module instructions and assessment criteria.

The frontend, Docker configuration, CI workflow and project-specific agent instructions are intentionally absent. Create them during the appropriate milestones. For later frontend work the course uses Node 22.12+/npm and React/Vite.

Use the taught Codex or Claude Code workflow: inspect relevant source, plan a small change, review its diff, run checks and commit. Author AGENTS.md/CLAUDE.md in Module 3 and preserve a real before/after comparison. Agent assistance does not replace your verification or understanding.

Keep one [evidence log](EVIDENCE.md) throughout the course. There are no weekly capstone uploads. The final submission includes your repository and recording; see [assessment and final demonstration](ASSESSMENT.md).

As you implement the project, update this README with your actual setup, tests, configuration and deployment instructions. Later modules assess whether those instructions work from a clean clone.
