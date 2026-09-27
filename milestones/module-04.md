# Module 4 — Build and verify the first feature

[Project overview](../README.md) · [Workflow](../STUDENT_WORKFLOW.md) · [Rubric PDF](../rubrics/PromptLab_Module_4_Project_Rubric.pdf)

Continue from your documented and specified Module 3 application. Implement your chosen first feature, normally version history.

1. Work in small increments. For each increment, commit a meaningful failing test and capture its result before implementing the behavior that makes it pass. Preserve the actual red-to-green history.
2. Add meaningful endpoint success/failure cases and storage, utility and model assertions. Reach at least 80% coverage; coverage alone does not establish test quality.
3. Identify a concrete code smell and perform a named, behavior-preserving refactor. Keep before/after commit hashes and passing checks; preserve observable behavior and interfaces.
4. Configure lint, tests and the 80% coverage gate in CI on pushes/pull requests. Preserve an actual successful run, deliberate failure and recovery. Configure and document the required merge check separately in GitHub; a workflow file alone does not prove it.
5. Create backend/Dockerfile and root docker-compose.yml, and document reproducible build/run and development hot reload. Verify the container serves the API from committed files.
6. Reconcile both feature specs, API reference, docstrings and README with your implemented state. Identify the second feature as planned until Module 5.

Record tests, coverage, red/green commits, refactor checks, hosted CI links/results, merge-rule proof and container verification in EVIDENCE.md. Run checks yourself; no supplied grader suite is included.

**Criteria:** C2.4–C2.8, plus final review of C2.1/C2.2. C2.4 and C2.7 are MUST PASS. Mark the snapshot `module-4-complete`. Keep this application for Module 5; there is no weekly upload.

[Evidence log](../EVIDENCE.md) · [Assessment policy](../ASSESSMENT.md)
