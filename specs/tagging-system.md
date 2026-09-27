# Prompt tagging — learner specification

Complete before implementation. Questions guide your decisions; they do not prescribe API answers.

## Overview and goals

Problem, intended user and scope:

## User stories and acceptance criteria

For each story state observable success and failure. Write criteria precise enough to become assertions.

| Story | Given / When / Then | Success example | Failure/edge example |
|---|---|---|---|
| | | | |

## Design decisions

- How are tags represented and related to prompts?
- How do creation, assignment, unassignment and deletion work?
- What normalization, case sensitivity, duplicate policy and limits are justified?
- How does filtering interact with existing collection filtering and text search?
- What happens for invalid identifiers, empty values, duplicate assignment and unknown tags?

Record your answers and rationale here:

## Data model

Fields, types, relationships, constraints, defaults and lifecycle:

## API contract

| Method/path | Request shape/example | Response/status/example | Errors/status/shape | Acceptance criterion |
|---|---|---|---|---|
| | | | | |

Every endpoint needs at least one directly testable acceptance criterion. Include errors and edge cases,
not just happy paths. Planned routes remain here until implemented; only real routes enter API_REFERENCE.

## Implementation order and evidence

Chosen first/second feature and reason:
Spec commit before implementation:
For each increment: red-test commit/result → implementation commit/result → refactor if needed:
Spec changes, reasons and corresponding updated tests/docs:
