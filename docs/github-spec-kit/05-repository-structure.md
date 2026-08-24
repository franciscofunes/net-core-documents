# Spec Kit project folder structure

The exact scaffolding depends on the selected integration and Spec Kit version, but the following structure is the useful mental model for the GitHub Copilot Skills path used in the presentation.

```text
financial-angular-app/
|
+-- .github/
|   +-- skills/
|       +-- speckit-specify/
|       |   +-- SKILL.md
|       +-- speckit-plan/
|       |   +-- SKILL.md
|       +-- speckit-tasks/
|       |   +-- SKILL.md
|       +-- speckit-analyze/
|       |   +-- SKILL.md
|       +-- speckit-implement/
|       |   +-- SKILL.md
|       +-- ...
|
+-- .specify/
|   +-- memory/
|   |   +-- constitution.md
|   +-- extensions/
|   +-- workflows/
|   +-- project/integration state and shared infrastructure
|
+-- specs/
|   +-- NNN-export-reporting/
|       +-- spec.md
|       +-- plan.md
|       +-- tasks.md
|       +-- checklists/
|           +-- requirements.md
|           +-- other reviewer checklists
|
+-- src/
|   +-- app/
|       +-- existing Angular application
|
+-- ...
```

## What each area means

### `.github/skills/`

For the current GitHub Copilot integration, Skills are the default representation. Spec Kit installs `speckit-<command>/SKILL.md` under `.github/skills/`.

These are **agent capabilities/instructions**, not the business specification itself.

An alternative supported commands layout can use:

```text
.github/agents/*.agent.md
.github/prompts/*.prompt.md
.vscode/settings.json
```

Do not confuse that legacy/supported commands representation with the Skills path used for the main presentation story.

### `.specify/`

Project-level Spec Kit infrastructure and state live under `.specify/`.

Relevant concepts include:

- persistent project principles / Constitution
- installed extensions and their config
- workflow state / overlays
- integration/catalog configuration
- shared infrastructure managed by the CLI

The DeepWiki material used for the theory slide describes `constitution.md` under `.specify/memory/`.

### `specs/<feature>/`

This is where feature intent becomes durable repository context.

Key artifacts:

- `spec.md` — WHAT / WHY
- `plan.md` — HOW
- `tasks.md` — dependency-ordered implementation work
- `checklists/` — requirement-quality review artifacts

These files are important because they connect one workflow stage to the next without relying only on chat history.

### `src/` (or equivalent application folders)

This is the actual brownfield codebase. In the presentation scenario, it is an existing financial Angular application containing the Reporting Dashboard.

Spec Kit does not replace the application architecture. The coding agent must understand and respect the existing components, services, API patterns, permissions, tests, and UX conventions when implementing the feature.

## Simple flow from command to file

```text
/speckit-specify  -> specs/.../spec.md
/speckit-plan     -> specs/.../plan.md
/speckit-tasks    -> specs/.../tasks.md
/speckit-implement -> application source code
/speckit-converge -> verify code against spec/plan/tasks; append missing tasks if needed
```

## Sources

- https://github.com/github/spec-kit/blob/main/docs/reference/integrations.md
- https://github.com/github/spec-kit/blob/main/docs/reference/agentic-sdd.md
- https://github.com/github/spec-kit/blob/main/docs/reference/extensions.md
- https://github.com/github/spec-kit/blob/main/docs/reference/workflows.md
- DeepWiki PDF: *Spec-Driven Development | github/spec-kit*.
