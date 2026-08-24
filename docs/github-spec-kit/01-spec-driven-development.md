# Spec-Driven Development (SDD)

## One-sentence definition

Spec-Driven Development is a development approach where specifications and implementation plans become durable, executable assets that guide AI-assisted implementation instead of being disposable documentation.

GitHub describes Spec Kit as an open-source toolkit for building high-quality software with AI coding agents using a ready-to-use spec-driven process that can also be customized or replaced.

## Power inversion

Traditional software development often treats code as the ultimate source of truth. Requirements documents and design documents can drift once coding starts.

SDD inverts this relationship:

```text
Traditional
requirements -> implementation -> code becomes truth

SDD
intent -> specification -> plan -> implementation
                    ^
                    |
            code serves the spec
```

The presentation should emphasize three ideas:

### 1. Specifications as executable assets

The specification and implementation plan are precise enough to guide an AI coding agent toward working implementation.

### 2. Intent-driven development

The first concern is the **what** and **why** — the desired behavior, users, outcomes, and constraints. Technology choices belong later in the plan.

### 3. Single source of truth

Maintaining the software means maintaining the specification and plan as the product evolves. If behavior is wrong, the error may be in implementation, specification, or planning.

## The critical separation: `spec.md` vs `plan.md`

This is one of the most important ideas for the talk.

| Artifact | Focus | Typical content |
|---|---|---|
| `spec.md` | WHAT / WHY | functional requirements, user stories/scenarios, success criteria, expected behavior |
| `plan.md` | HOW | technology stack, architecture, dependencies, storage, platform, implementation choices |

The spec should not prematurely encode the technology stack. The same business requirement can theoretically be implemented with different technical approaches without rewriting its functional intent.

## Why this matters for AI-assisted development

A one-shot prompt asks the model to infer requirements and implementation at the same time. SDD separates those decisions and turns them into persistent artifacts that can be reviewed before coding.

A useful presentation line:

> We are not asking AI to decide what we are building while it is already building it.

## Prompt engineering vs context engineering

Do not say prompt engineering is dead. A more accurate statement is:

> The prompt is no longer responsible for carrying all the context.

A good initial prompt still matters because it expresses intent. But the coding agent can also work from project principles, feature specifications, plans, tasks, repository structure, code, and context-management mechanisms.

This shifts the emphasis from optimizing one perfect prompt toward engineering the context and workflow around the agent.

## Sources

- https://github.com/github/spec-kit/blob/main/README.md
- https://github.com/github/spec-kit/blob/main/docs/reference/agentic-sdd.md
- DeepWiki PDF: *Spec-Driven Development | github/spec-kit* used as theory source during presentation preparation.
