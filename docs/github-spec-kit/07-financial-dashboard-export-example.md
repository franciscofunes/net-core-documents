# Brownfield Angular example: Export to Excel from Reporting Dashboard

## Scenario

Existing financial application built with Angular.

Jira request:

> Add Export to Excel to the Reporting Dashboard table.

Expected behavior for the presentation:

- respect active dashboard filters
- export all matching reporting rows, not only the visible page
- preserve the expected reporting columns
- follow existing permissions and UX behavior
- reuse existing application patterns where possible

## Why this is a strong brownfield example

Creating an Excel file is not the hard part. The hard part is adding the feature without inventing new behavior or breaking the architecture of an application that already exists.

Questions that may need clarification:

- Which rows are exported?
- Which columns are exported?
- Do hidden UI columns export?
- Is there a maximum export size?
- Who is allowed to export?
- What happens while the export is being prepared?
- What happens when the export fails?
- Does the application already have an export or download utility?

## Practical Spec Kit flow

### Specify

Start with enough business intent to create a useful first specification. Do not try to encode the entire architecture into the first instruction.

Example intent:

> Add Export to Excel to the existing Reporting Dashboard table. The export must respect active dashboard filters and export all matching reporting rows, not only the current visible page. Follow the existing permissions and user experience of the financial application.

### Review and Clarify

Read `spec.md`, then use the Clarify stage to remove meaningful ambiguity: export scope, reporting columns, permissions, large result sets, filename behavior, loading state, and error behavior.

### Plan

This is where brownfield repository context becomes central. The coding agent should investigate the existing application before proposing implementation choices:

- Reporting Dashboard component structure
- current table and filter state
- data/query services
- permissions
- notification conventions
- API patterns
- existing export/download utilities
- testing conventions
- architecture/dependency constraints

### Checklist

Use a requirements-quality checklist when the feature needs an explicit review gate. Useful checks include whether export scope, columns, authorization, empty results, large result sets, loading states, and error states are unambiguous.

### Tasks

Generate dependency-ordered work from the approved spec and plan. Conceptually this may include the export action, filter propagation, service/API work, download behavior, loading/error handling, and tests.

### Analyze

Use the Analyze stage before implementation to detect contradictions or missing coverage across `spec.md`, `plan.md`, and `tasks.md`.

### Implement

Implementation is where the coding agent uses its normal development tools to read/search the repository, edit the Angular code, run commands, and run tests.

### Converge

Converge verifies the implementation against the specification, plan, and tasks. If gaps are found, new tasks can be appended and implementation runs again until the feature converges.

## Time/productivity message

Do not claim an unsupported percentage.

Use:

> More structured context before coding can reduce clarification and rework loops and make delivery more predictable.

The key idea is that requirement and design problems are moved earlier, when they are cheaper to correct.
