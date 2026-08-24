# Five-minute presentation script

## Slide 1 — What Spec-Driven Development changes (~1 minute)

GitHub Spec Kit implements Spec-Driven Development. The core idea is a power inversion.

Traditionally, code becomes the source of truth and requirements or design documents can become outdated. In SDD, the specification and implementation plan become durable assets that guide implementation.

The developer starts with intent — the **what** and **why** — before deciding the **how**.

That separation is important:

- `spec.md` contains functional requirements, user scenarios, and success criteria.
- `plan.md` contains the technology stack, architecture, dependencies, and implementation decisions.

This is also why I would not describe this as only prompt engineering. The prompt still matters, but it is no longer responsible for carrying all the context. The focus shifts toward engineering the context and workflow around the coding agent.

## Slide 2 — The complete Spec Kit flow (~1.5 minutes)

At project level, we have the Constitution. In our scenario this has already been created and merged to `main`, so we do not recreate it for every feature. It provides the project principles that later work should respect.

At feature level, we start with Specify, which creates the business specification. Clarify removes ambiguity and writes answers back into the spec.

Plan is where implementation details enter and where the agent maps the feature to the technology and architecture.

Checklist is a requirements-quality review — the official reference describes it as unit tests for requirements.

Tasks then turns the plan into dependency-ordered work. Analyze is a read-only consistency check across the spec, plan, and tasks.

Implement executes the tasks. Finally, Converge checks the actual code against the artifacts. If it finds gaps, it appends new tasks, we implement again, and repeat until the feature converges.

So this is not just a linear sequence. It has refinement, gates, and a verification loop.

## Slide 3 — What I actually do in VS Code (~2 minutes)

Now make it practical.

We have an existing financial Angular application and receive a Jira ticket: add Export to Excel to the Reporting Dashboard table.

The export must respect active dashboard filters and export all matching reporting rows, not just the visible page.

I open the existing solution in VS Code and use GitHub Copilot Chat. For the presentation I focus on the Copilot Skills path: Copilot is the coding agent, and Spec Kit exposes specialized capabilities for the stages of the workflow.

I start with Specify. I do not need a giant perfect prompt. I need enough business intent to create a useful first `spec.md`.

Then I review that specification and use Clarify for questions such as: which reporting columns are included, permissions, large result sets, loading behavior, and error behavior.

Next comes Plan. This is where brownfield context becomes critical. The coding agent investigates the existing Reporting Dashboard, filter state, services, permissions, API patterns, export utilities, tests, and architecture so the change fits the application rather than inventing a new pattern.

Tasks turns the approved plan into executable work. Checklist and Analyze give us quality gates before coding.

Implement is when Copilot uses its normal tools to search/read files, edit code, run commands, and run tests.

Finally, Converge checks the implementation against the specification, plan, and tasks. If there is a gap, we loop back through new tasks and implementation.

The key message is: **we do not jump directly from Jira to generated code.** We progressively build and verify context before implementation.

## Optional ~20 second context-engineering addition

Another important piece is persistent context. Spec Kit does not rely only on the current chat. Project principles, feature specifications, plans, tasks, checklists, and the existing codebase all live as repository context. Spec Kit also has agent-context mechanisms that can maintain managed agent instruction sections pointing to the active plan.

A simple way to summarize this is:

> Agentic Development = Model + Context + Tools + Workflow + Feedback.

GitHub Copilot provides the coding-agent environment and development tools. Spec Kit structures much of the context, workflow, quality gates, and feedback loop.

## Q&A: Is this multi-agent?

The default SDD flow does not require a group of agents communicating with one another. A simpler model is one coding agent using different Spec Kit capabilities and shared repository artifacts.

Spec Kit can become more automated through extensions, presets, workflows, and bundles. Workflows can add conditions, loops, shell steps, human checkpoints, fan-out/fan-in, and pause/resume behavior, so the same harness can support more sophisticated agentic processes.

## Q&A: Does the first prompt need to be long?

No. Prompt quality still matters, but length is not the goal. Start with clear business intent, review the generated specification, and use Clarify and Checklist to improve requirement quality before planning and implementation.

## Q&A: What is the productivity claim?

Do not claim a fixed percentage unless the team has measured it.

Use:

> More structured context before coding can reduce clarification and rework loops and make delivery more predictable.
