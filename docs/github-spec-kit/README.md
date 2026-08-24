# GitHub Spec Kit research pack

This folder collects the material needed to explain GitHub Spec Kit, Spec-Driven Development (SDD), GitHub Copilot integration, context engineering, and a practical brownfield Angular example for a short presentation.

## Purpose

The goal is to make the research available from an isolated VDI without depending on prior chat history. The content is intentionally separated into small Markdown files so PowerPoint Copilot or another assistant can use only the context needed for a slide.

## Recommended reading order

1. [01-spec-driven-development.md](01-spec-driven-development.md) — the core SDD philosophy and separation of `spec.md` vs `plan.md`.
2. [02-complete-sdd-workflow.md](02-complete-sdd-workflow.md) — Constitution, Specify, Clarify, Plan, Checklist, Tasks, Analyze, Implement, Converge.
3. [03-copilot-skills-and-integrations.md](03-copilot-skills-and-integrations.md) — how Spec Kit integrates with GitHub Copilot and why Skills are the preferred presentation path.
4. [04-context-engineering-and-memory.md](04-context-engineering-and-memory.md) — persistent project context, feature artifacts, agent-context management, and the context-engineering framing.
5. [05-repository-structure.md](05-repository-structure.md) — where the important files live in a Spec Kit project.
6. [06-agentic-evolution.md](06-agentic-evolution.md) — extensions, presets, workflows, bundles, and how SDD can become more automated/agentic.
7. [07-financial-dashboard-export-example.md](07-financial-dashboard-export-example.md) — the practical brownfield Angular scenario used in the talk.
8. [presentation-script.md](presentation-script.md) — compact ~5 minute script.
9. [powerpoint-copilot-prompt.md](powerpoint-copilot-prompt.md) — self-contained prompt for generating the slides in PowerPoint Copilot.

## Core mental model

> GitHub Copilot is the coding-agent environment. Spec Kit provides an extensible Spec-Driven Development process, persistent artifacts, context-management mechanisms, quality gates, and workflow primitives that guide the agent from intent to verified implementation.

The prompt is important, but it is no longer responsible for carrying all context. Context also comes from the Constitution, `spec.md`, `plan.md`, `tasks.md`, the existing codebase, project state, and optional agent-context synchronization.

## Primary sources

The research was checked against the current `github/spec-kit` repository on `main` and the DeepWiki SDD PDF used during preparation.

Useful upstream references:

- https://github.com/github/spec-kit
- https://github.com/github/spec-kit/blob/main/README.md
- https://github.com/github/spec-kit/blob/main/docs/reference/agentic-sdd.md
- https://github.com/github/spec-kit/blob/main/docs/reference/integrations.md
- https://github.com/github/spec-kit/blob/main/docs/reference/extensions.md
- https://github.com/github/spec-kit/blob/main/docs/reference/workflows.md
- https://github.com/github/spec-kit/blob/main/docs/reference/overview.md
- https://github.com/github/spec-kit/blob/main/extensions/agent-context/commands/speckit.agent-context.update.md

## Presentation accuracy notes

- Do not call Spec Kit a single AI agent. It is an open-source toolkit / extensible harness for SDD and related agentic workflows.
- Do not describe the standard SDD flow as many agents talking to each other. A safer model is one coding agent using specialized Spec Kit capabilities and persistent repository artifacts between stages.
- Do not say prompt engineering is literally dead. Prefer: **the prompt is no longer responsible for carrying all the context**.
- Do not invent a time-saving percentage. Say that more structured context and earlier quality gates can reduce clarification/rework loops and improve predictability.
