# Complete Spec Kit SDD workflow

The current Spec Kit reference describes an agentic SDD sequence:

```text
/speckit.constitution
  -> /speckit.specify
  -> /speckit.clarify
  -> /speckit.plan
  -> /speckit.checklist
  -> /speckit.tasks
  -> /speckit.analyze
  -> /speckit.implement
  -> /speckit.converge
```

The commands are designed to run in order, although only `specify` is strictly required before `plan`. Clarify, checklist, and analyze are quality gates that are especially valuable when the feature has meaningful ambiguity.

## 0. Constitution — project level

`/speckit.constitution` creates or updates the project Constitution: principles that later stages are evaluated against.

For the presentation scenario, Constitution is already established and merged to `main`; it is not recreated for each feature.

Typical concerns:

- code quality
- testing standards
- security
- UX consistency
- performance
- architecture principles

## 1. Specify — WHAT and WHY

`/speckit.specify` creates or updates the feature specification from natural language.

Focus on:

- user-facing behavior
- goals
- business constraints
- prioritized user stories
- success criteria

Avoid prematurely deciding the tech stack.

Spec Kit may also maintain `checklists/requirements.md`, a built-in specification-quality checklist. This is separate from custom checklists created with `/speckit.checklist`.

## 2. Clarify — remove ambiguity

`/speckit.clarify` asks targeted questions about underspecified parts of the current specification and writes the answers back into `spec.md`.

It can be run repeatedly, each time with a different focus.

Important principle:

> Clarify before designing on top of ambiguity.

If later analysis discovers a requirement gap, return to `specify` or `clarify` rather than hiding the issue in implementation.

## 3. Plan — HOW

`/speckit.plan` turns the approved requirements into technical design artifacts.

This is where implementation details belong:

- framework / language
- architecture
- dependencies
- storage
- service/API approach
- project structure
- brownfield reuse strategy

The DeepWiki SDD material highlights a Constitution Check as a planning gate before research and design.

## 4. Checklist — requirements-quality review

`/speckit.checklist` generates a custom checklist for reviewing requirement quality. The official reference describes this as **"unit tests for your requirements."**

It checks whether requirements are complete, clear, unambiguous, and consistent.

A custom checklist is reviewer-owned. Implementation must not silently self-approve it.

If a checklist reveals gaps, loop back to `clarify` or `specify` before continuing.

## 5. Tasks — dependency-ordered work

`/speckit.tasks` generates `tasks.md` from the design artifacts.

Current task organization includes:

- Setup
- Foundational blockers
- one phase per user story in priority order
- Polish / cross-cutting work

Tasks may be marked for parallel execution where possible.

## 6. Analyze — cross-artifact consistency

`/speckit.analyze` is read-only. It checks `spec.md`, `plan.md`, and `tasks.md` for conflicts, gaps, ambiguity, or missing coverage.

Examples:

- a task with no matching requirement
- a plan decision that contradicts the spec
- a requirement with no implementation task

If a problem is found, fix it in the artifact that owns the decision, then re-run analyze.

## 7. Implement — execute the task plan

`/speckit.implement` executes tasks in dependency order and respects parallel markers.

Before executing, it reads checklist state as a gate. If checklist items remain unchecked, it asks before proceeding; it does not silently mark checklist items complete.

For a large feature, implementation can be scoped to a subset of phases to avoid overwhelming the agent context.

## 8. Converge — verify and loop

`/speckit.converge` checks the codebase against the feature's spec, plan, and tasks.

It is append-only with respect to feature artifacts: if it finds missing work, it can append tasks to `tasks.md`. It does not edit/delete code.

Two outcomes:

```text
Converged -> done / review / PR

Gaps found -> append tasks -> implement -> converge again
```

The README explicitly recommends repeating Implement + Converge until Converge reports **Converged**.

## Presentation-friendly diagram

```text
PROJECT LEVEL
Constitution (already on main)
        |
        v
FEATURE LEVEL
Jira / business intent
        |
        v
Specify -> spec.md
        |
     Clarify
        |
        v
Plan -> plan.md
        |
   Checklist gate
        |
        v
Tasks -> tasks.md
        |
      Analyze
        |
        v
Implement -> code
        |
        v
Converge
   |          |
 gaps      converged
   |          |
 tasks       done
   |
Implement again
```

## Sources

- https://github.com/github/spec-kit/blob/main/docs/reference/agentic-sdd.md
- https://github.com/github/spec-kit/blob/main/README.md
- DeepWiki PDF: *Spec-Driven Development | github/spec-kit*.
