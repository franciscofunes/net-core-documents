# Five-minute presentation guion — aligned to the 3 final slides

Use this as a read-aloud guide. Do not read every label that is already visible. Follow the visual order of each slide and use the script to explain the meaning behind the diagram.

## Slide 1 — What Spec-Driven Development changes (~1 minute 20 seconds)

GitHub Spec Kit implements what GitHub calls **Spec-Driven Development**, or SDD.

The main idea is the **power inversion** shown here.

In traditional development, requirements and design documents support the code, but over time the code usually becomes the real source of truth. That creates a risk: the supporting documentation can drift out of date.

Spec-Driven Development reverses that relationship.

We start with **intent** — the what and why. From that intent we create `spec.md`, which describes the functional requirements, user scenarios and success criteria.

Only after that do we move to `plan.md`, where we decide the **how**: architecture, technology, dependencies and implementation decisions.

Then implementation follows the agreed plan.

So the important separation on this slide is simple:

- `spec.md` is **WHAT + WHY**.
- `plan.md` is **HOW**.

And this connects directly to modern AI development. Prompt quality still matters, but the prompt is no longer responsible for carrying all of the context.

The context also comes from project principles, specifications, plans, tasks and the existing repository.

That is why I see Spec Kit as moving us beyond one-shot prompt engineering toward **engineering the context and workflow around the coding agent**.

## Slide 2 — The complete Spec Kit flow (~1 minute 40 seconds)

This slide shows the complete lifecycle, but the first distinction is **project level versus feature level**.

At project level we have the **Constitution**. In our case, this is already created and merged into `main`, so we do not recreate it for every feature. It defines principles and constraints that every later feature should respect.

Then, at feature level, I think about the flow in four groups: **Define, Design, Deliver and Verify**.

Under **Define**, Specify creates the first business specification, and Clarify removes ambiguity by asking targeted questions and writing the answers back into the spec.

Under **Design**, Plan maps the approved requirements to the technology and architecture of the real application. Checklist then reviews the quality and completeness of those requirements.

Under **Deliver**, Tasks turns the plan into dependency-ordered work. Analyze cross-checks the specification, plan and tasks, and Implement executes the approved work.

Finally, under **Verify**, Converge compares the actual code with the artifacts.

The important part is the loop at the bottom: if Converge finds gaps, we add tasks, implement again, and re-check until the code and the artifacts converge.

So this is not just eight slash commands in a row. It is a workflow with **refinement, quality gates and feedback**.

And the stages are not starting from zero every time. They share persistent repository artifacts such as the Constitution, `spec.md`, `plan.md`, `tasks.md`, checklists and the existing codebase.

That is the context-engineering aspect of the toolkit: **the prompt is one source of context, not the whole context**.

## Slide 3 — What I actually do in VS Code (~1 minute 50 seconds)

Now I want to connect the theory to what the developer actually experiences.

Imagine I receive this Jira ticket for an existing financial Angular application:

**Add Export to Excel to the Reporting Dashboard.**

The main business constraints are already visible here: respect the active filters, export every matching row, and do not limit the export to the currently visible page.

I open the existing solution in Visual Studio Code and use GitHub Copilot Chat in Agent mode.

For this example, **Copilot is the coding agent**, and Spec Kit gives that agent the structure around the workflow.

The first practical step is **Specify plus Clarify**.

I start with enough business intent to generate a useful first spec. I do not need a giant perfect prompt. Then I review the spec and clarify things such as which columns are included, permissions, scale, loading behavior and error handling.

Next is **Plan**.

This is especially important because this is a brownfield application. The agent investigates the existing Reporting Dashboard, filter state, Angular services, API patterns, authorization, export utilities, tests and architecture.

The goal is not to invent a new architecture. The goal is to make the new feature fit the application we already have.

Then **Tasks plus Gates** turns that approved plan into ordered work and checks for gaps before coding.

During **Implement**, Copilot uses its normal coding-agent tools: it searches and reads files, edits code, runs commands and executes tests.

Finally, **Converge** compares the result against the specification, plan and tasks. If a gap remains, it becomes new work and the loop repeats.

So the key message on this slide is the one at the bottom:

> **We do not jump from Jira directly to generated code. We progressively build and verify context before implementation.**

And that is why a useful mental model for this is:

> **Agentic Development = Model + Context + Tools + Workflow + Feedback.**

GitHub Copilot gives us the coding-agent environment and tools. Spec Kit structures much of the context, workflow, quality gates and verification around that agent.

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
