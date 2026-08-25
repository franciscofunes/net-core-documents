# Five-minute presentation guion — 3 slides

This is the read-aloud version for a three-slide presentation. Keep the pace conversational. Do not read every label on the slide; use the slide as the visual map and use this script to explain the story.

## Slide 1 — What Spec-Driven Development changes (~1 minute 20 seconds)

GitHub Spec Kit implements what GitHub calls **Spec-Driven Development**, or SDD.

The central idea is a power inversion.

Traditionally, we start with requirements or design documents, then we implement, and over time the code becomes the real source of truth. The risk is that the original documentation becomes outdated.

With Spec-Driven Development, the specification and implementation plan become durable artifacts that continue guiding the implementation.

The developer starts with the **what and why**, before deciding the **how**.

That separation is important.

`spec.md` describes the functional requirements, user scenarios and success criteria. It focuses on what the system should do.

`plan.md` describes how we are going to implement it: architecture, technologies, dependencies and technical decisions.

This also changes how I think about AI-assisted development. Prompt quality still matters, but the prompt is no longer responsible for carrying all the context.

The context also comes from the Constitution, the specification, the plan, the tasks, the existing repository and the project state.

So the focus shifts from trying to craft one perfect prompt to **engineering the context and workflow around the coding agent**.

## Slide 2 — The complete Spec Kit workflow and context (~1 minute 40 seconds)

At project level we have the **Constitution**.

In our case, that is already created and merged into `main`, so we do not recreate it for every feature. It acts as persistent project context and defines principles and constraints that later work should respect.

For each new feature, we start with **Specify**. We give Spec Kit a natural-language description and it creates the first `spec.md`.

Then **Clarify** helps detect ambiguity, asks targeted questions and writes the answers back into the specification. This is why the first prompt does not need to be perfect.

Next comes **Plan**. This is where the technical implementation enters. The agent maps the approved business requirements to the real architecture, dependencies and technology of the application. The plan also checks alignment with the Constitution.

Then **Checklist** reviews requirement quality, and **Tasks** converts the plan into dependency-ordered executable work.

**Analyze** can check consistency across the specification, plan and tasks before implementation.

Then **Implement** executes those tasks.

Finally, **Converge** compares the real code against the artifacts. If something is missing, it can add new tasks and we go through the loop again.

So this is not just a sequence of slash commands. It is a workflow with refinement, quality gates and feedback.

And importantly, the stages share persistent repository artifacts: the Constitution, `spec.md`, `plan.md`, `tasks.md`, checklists and the existing codebase. Spec Kit also has agent-context mechanisms that keep relevant project state available to the coding agent.

That is the context-engineering part: **the prompt is one source of context, not the whole context**.

## Slide 3 — What I actually do in VS Code (~1 minute 45 seconds)

Now let us make it practical.

Imagine I receive a Jira ticket for an existing financial Angular application.

The requirement is to add **Export to Excel** to the Reporting Dashboard table.

The export should respect the active dashboard filters and export all matching reporting rows, not only the rows visible on the current page.

I open the existing solution in Visual Studio Code and use GitHub Copilot Chat in Agent mode.

For this example, **Copilot is the coding agent** and Spec Kit gives that agent a structured workflow and reusable capabilities.

I start with `speckit-specify` and provide enough business intent to create a useful first specification. I do not need a giant perfect prompt.

Then I read `spec.md`.

If something is unclear, I use Clarify. For example: which reporting columns should be exported? Does it include all filtered rows? Are there permissions? What happens with large datasets? What happens if the export fails?

Once the business behavior is clear, I run Plan.

This is especially important in a brownfield application. The coding agent now investigates the existing Reporting Dashboard, filter state, Angular services, API patterns, authorization, tests and any existing export utilities.

The goal is not to invent a new architecture. The goal is to make the feature fit the application we already have.

Tasks converts the approved plan into executable work. Checklist and Analyze give us quality checks before coding.

Implement is when Copilot uses its normal tools: search files, read code, edit files, run commands and execute tests.

Finally, Converge verifies that the implementation still matches the specification and plan.

The key message is:

> **We do not jump directly from Jira to generated code.**

We progressively create, refine and verify the context before implementation.

A simple way to summarize the model is:

> **Agentic Development = Model + Context + Tools + Workflow + Feedback.**

GitHub Copilot provides the coding-agent environment and development tools. Spec Kit structures much of the context, workflow, quality gates and verification around that agent.

## Closing (~10 seconds)

Spec Kit is not about replacing developers with a better prompt. It gives us a structured way to move from business intent to implementation while keeping requirements, technical decisions, tasks and code connected.

## Q&A — Is this multi-agent?

Not by default. The simplest mental model is one coding agent using different Spec Kit capabilities and shared repository artifacts.

Spec Kit can later become more automated through extensions, presets, workflows and bundles, including more sophisticated orchestration.

## Q&A — Does the first prompt need to be long?

No. Prompt quality still matters, but length is not the goal. Start with clear business intent, review the generated specification, and use Clarify and Checklist to improve requirement quality before planning and implementation.

## Q&A — What is the productivity claim?

Do not claim a fixed percentage unless the team has measured it.

Use:

> More structured context before coding can reduce clarification and rework loops and make delivery more predictable.
