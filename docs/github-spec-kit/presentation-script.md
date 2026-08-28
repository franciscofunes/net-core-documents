# Five-minute presentation guion — final 4-slide version

Use this as a natural read-aloud guide. Do not read every label already visible on the slides; use the script to explain what the visuals mean.

## Slide 1 — What Spec-Driven Development changes (~1 minute)

GitHub Spec Kit implements what GitHub calls **Spec-Driven Development**.

The core idea is a **power inversion**.

In traditional development, requirements and design documents support the implementation, but over time the code often becomes the real source of truth. The risk is that the documentation can drift out of date.

With Spec-Driven Development, we reverse that relationship. We start from **intent — the what and why**.

That intent becomes `spec.md`, which contains the functional requirements, user scenarios and success criteria.

Then we move to `plan.md`, which defines the **how**: architecture, technologies, dependencies and implementation decisions.

So the simple distinction is:

- `spec.md` is **WHAT + WHY**.
- `plan.md` is **HOW**.

And this is where the context-engineering idea becomes important.

The prompt still matters, but it is no longer responsible for carrying all the context. The context also lives in project principles, specifications, plans, tasks and the existing repository.

So instead of trying to write one perfect prompt, we progressively build the context around the coding agent.

## Slide 2 — The complete Spec Kit flow (~1 minute 20 seconds)

This slide shows the complete workflow.

The first distinction is between **project level and feature level**.

At project level, we have the **Constitution**.

In our case, the Constitution is already created and merged into `main`. We do not recreate it for every feature. It defines the project principles and constraints that every later feature should respect.

Then at feature level, I group the workflow into four areas: **Define, Design, Deliver and Verify**.

Under **Define**, Specify creates the first business specification. Clarify helps remove ambiguity and writes those decisions back into the specification.

Under **Design**, Plan maps the requirements to the actual technology and architecture of the application. Checklist helps validate the quality and completeness of the requirements.

Under **Deliver**, Tasks converts the approved plan into dependency-ordered work. Analyze cross-checks the artifacts for inconsistencies. Implement executes the approved work.

Finally, under **Verify**, Converge compares the implementation with the specification, plan and tasks.

The important part is that this is a loop.

If Converge finds a gap, we create or refine tasks, implement again, and verify again.

So this is not just a sequence of slash commands. It is a structured workflow with **refinement, quality gates, persistent context and feedback**.

## Slide 3 — What I actually do in VS Code (~1 minute 30 seconds)

Now I want to move from the theory to the actual developer experience.

The example is an existing financial Angular application.

The Jira ticket is to add **Export to Excel to the Reporting Dashboard**.

The business requirements are that the export respects the active filters, exports all matching reporting rows, and does not only export the currently visible page.

I open the solution in Visual Studio Code and use GitHub Copilot Chat in Agent mode.

For this example, **Copilot is the coding agent**, and Spec Kit gives the workflow and persistent artifacts around it.

I start with **Specify and Clarify**.

I provide enough business intent to create a useful first specification. I do not need a giant perfect prompt.

Then I review the specification and clarify missing decisions, such as columns, permissions, loading states, error behavior and scale.

Next comes **Plan**.

This is especially important in a brownfield application. The agent investigates the existing Reporting Dashboard, filter state, Angular services, API patterns, authorization, export utilities, tests and architecture.

The goal is not to invent a new architecture. The goal is to fit the feature into what already exists.

Then **Tasks and Gates** turn the approved plan into executable work and validate it before coding.

During **Implement**, Copilot uses normal coding-agent tools like search, read, edit, terminal and tests.

Finally, **Converge** verifies the result against the artifacts.

So the key message is:

> **We do not jump from Jira directly to generated code. We progressively build and verify context before implementation.**

## Slide 4 — Real, reviewable artifacts (~1 minute)

This slide shows real evidence from that workflow.

On the left, we have **Analyze**.

This is a read-only consistency check. It compares the specification, plan, research and tasks, and produces structured findings with severity, exact locations and recommendations.

The important detail is that no code is modified at this stage.

In the middle, we have **Tasks and Gates**.

Here the approved intent becomes concrete work. We can see task IDs, prerequisites, phases, tests and actual file paths.

That makes the plan reviewable before the coding agent starts changing the application.

And on the right, we have **Implement**.

Before acting, Copilot loads the approved context and checks prerequisites and checklist status.

Only after those gates pass does it move from planning into action on the repository.

That is the point of this slide:

> **Artifacts first. Quality gates next. Code after.**

The reasoning is visible and reviewable before implementation begins.

## Closing (~10 seconds)

So the main takeaway is that Spec Kit is not about a better one-shot prompt.

It gives the coding agent **structured context, workflow, gates and feedback**, so we can move from business intent to implementation in a more controlled and reviewable way.

## Q&A — Is this multi-agent?

Not by default. The simplest mental model is **one coding agent using different Spec Kit capabilities and shared repository artifacts**.

Spec Kit can later become more automated through extensions, presets, workflows and bundles, including more sophisticated orchestration.

## Q&A — Does the first prompt need to be long?

No. Prompt quality still matters, but length is not the goal. Start with clear business intent, review the generated specification, and use Clarify and Checklist to improve requirement quality before planning and implementation.

## Q&A — What is the productivity claim?

Do not claim a fixed percentage unless the team has measured it.

Use:

> **More structured context before coding can reduce clarification and rework loops and make delivery more predictable.**
