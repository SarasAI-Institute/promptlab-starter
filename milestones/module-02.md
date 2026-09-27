# Module 2 — Investigate and repair

[Project overview](../README.md) · [Workflow](../STUDENT_WORKFLOW.md) · [Rubric PDF](../rubrics/PromptLab_Module_2_Project_Rubric.pdf)

Continue from the supplied backend. Read the source and CONTRACT.md before changing behavior.

1. Map routes, data flow, storage, relationships and dependencies. Explain why the context you supplied to the agent was relevant at each stage.
2. Keep at least two substantive prompt iterations, with the reason for each change. Record a real substantive AI mistake that you caught and how you verified the correction.
3. Repair the four inherited defects: missing-prompt 404 behavior, PUT timestamps, newest-first prompt ordering, and collection deletion leaving orphaned prompt references.
4. Implement partial PATCH according to CONTRACT.md, including omitted fields, explicit nulls, validation and missing IDs. Verify failures do not mutate stored data and repairs do not regress existing behavior.
5. Add accurate Google-style docstrings to changed functions and update the README so the project runs from a clean clone.

Record the system map, context decisions, prompt iterations, mistake/correction, verification results and commit references in EVIDENCE.md. Keep collection deletion behavior documented and tested; detach, cascade or prevention are permitted choices.

**Criteria:** C1.1–C1.6. C1.4 is MUST PASS. Mark your completed snapshot `module-2-complete`. Keep this same project for Module 3; there is no weekly upload.

[Evidence log](../EVIDENCE.md) · [Assessment policy](../ASSESSMENT.md)
