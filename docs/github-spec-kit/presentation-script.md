# Five-minute presentation guion — aligned to the 4-slide final story

Use this as a read-aloud guide. Do not read every label that is already visible. Follow the visual order of each slide and use the script to explain the meaning behind the diagram or screenshot.

## Slide 1 — What Spec-Driven Development changes (~1 minute 10 seconds)

GitHub Spec Kit implements what GitHub calls **Spec-Driven Development**, or SDD.

The main idea is the **power inversion** shown here.

In traditional development, requirements and design documents support the code, but over time the code usually becomes the real source of truth. That creates a risk: the supporting documentation can drift out of date.

Spec-Driven Development reverses that relationship.

We start with **intent** — the what and why. From that intent we create `spec.md`, which describes the functional requirements, user scenarios and success criteria.

Only after that do we move to `plan.md`, where we decide the **how**: architecture, technology, dependencies and implementation decisions.

Then implementation follows the agreed plan.

So the separation is simple:

- `spec.md` is **WHAT + WHY**.
- `plan.md` is **HOW**.

And this changes how I think about AI-assisted development. Prompt quality still matters, but the prompt is no longer responsible for carrying all the context.

The context also comes from the Constitution, the specification, the plan, the tasks and the existing repository.

That is why I see Spec Kit as moving us beyond one-shot prompt engineering toward **engineering the context and workflow around the coding agent**.

## Slide 2 — The complete Spec Kit flow (~1 minute 30 seconds)

This slide shows the full lifecycle, but the first distinction is **project level versus feature level**.

At project level we have the **Constitution**. In our case, this is already created and merged into `main`, so we do not recreate it for every feature. It defines principles and constraints that every later feature should respect.

Then, at feature level, I group the flow into four parts: **Define, Design, Deliver and Verify**.

Under **Define**, Specify creates the first business specification, and Clarify removes ambiguity by asking targeted questions and writing the answers back into the spec.

Under **Design**, Plan maps the approved requirements to the technology and architecture of the real application. Checklist reviews the quality and completeness of those requirements.

Under **Deliver**, Tasks converts the plan into dependency-ordered work. Analyze cross-checks the specification, plan and tasks, and Implement executes the approved work.

Finally, under **Verify**, Converge compares the actual code with the artifacts.

The important part is the feedback loop: if Converge finds gaps, we add or refine tasks, implement again, and re-check until the code and the artifacts converge.

So this is not just a sequence of slash commands. It is a workflow with **refinement, quality gates, persistent context and feedback**.

And the stages are not starting from zero each time. They share durable repository artifacts such as the Constitution, `spec.md`, `plan.md`, `tasks.md`, checklists and the existing codebase.

That is the context-engineering aspect of the toolkit: **the prompt is one source of context, not the whole context**.

## Slide 3 — What I actually do in VS Code (~1 minute 30 seconds)

Now I want to connect the theory to what the developer actually experiences.

Imagine I receive a Jira ticket for an existing financial Angular application:

**Add Export to Excel to the Reporting Dashboard.**

The business constraints are visible here: respect the active dashboard filters, export every matching reporting row, and do not limit the export to the visible page.

I open the existing solution in Visual Studio Code and use GitHub Copilot Chat in Agent mode.

For this example, **Copilot is the coding agent**, and Spec Kit gives that agent the structured workflow, persistent artifacts and quality gates around the work.

I start with **Specify plus Clarify**. I provide enough business intent to create a useful first spec, then I review it and resolve ambiguity around columns, permissions, scale, loading and error behavior.

Next is **Plan**. This is especially important because this is a brownfield application. The agent investigates the existing dashboard, filter state, Angular services, authorization, API patterns, export utilities, tests and architecture.

The goal is not to invent a new architecture. The goal is to fit the feature into the application we already have.

Then **Tasks plus Gates** turns the approved plan into ordered work and checks for gaps before coding.

During **Implement**, Copilot uses its normal development tools: search, read, edit, terminal and tests.

Finally, **Converge** compares the result against the specification, plan and tasks. If something is missing, that becomes new work and the loop repeats.

So the key message is:

> **We do not jump from Jira directly to generated code. We progressively build and verify context before implementation.**

## Slide 4 — The workflow leaves real, reviewable artifacts (~1 minute 5 seconds)

This slide is the proof that the workflow is not just theory. These are real outputs from the Export-to-Excel example.

On the left is **Analyze**.

The screenshot shows a read-only specification analysis report. It cross-checks the artifacts and reports concrete inconsistencies with severity, exact locations and recommendations.

The important point is that this happens **before coding** and does not modify the codebase.

In the middle is **Tasks plus Gates**.

This is where the approved intent becomes executable work. The tasks are dependency-ordered, linked to concrete files and tests, and the checklist verifies that the specification is complete and ready.

So before Copilot starts writing code, we already have something a developer can review and challenge.

On the right is **Implement**.

The screenshot shows the implementation preflight. Copilot loads the approved feature context, checks prerequisites and checklist status, and only then moves into action using its normal coding-agent tools.

This is the practical meaning of the bottom message:

> **Artifacts first. Quality gates next. Code after.**

The reasoning stays visible and reviewable instead of disappearing inside one large prompt.

## Closing (~10 seconds)

Spec Kit gives us a structured path from business intent to verified implementation while keeping requirements, technical decisions, tasks and code connected.

A simple mental model is:

> **Agentic Development = Model + Context + Tools + Workflow + Feedback.**

GitHub Copilot provides the coding-agent environment and tools. Spec Kit structures much of the context, workflow, quality gates and verification around that agent.

## Q&A — Is this multi-agent?

Not by default. The simplest mental model is one coding agent using different Spec Kit capabilities and shared repository artifacts.

Spec Kit can later become more automated through extensions, presets, workflows and bundles, including more sophisticated orchestration.

## Q&A — Does the first prompt need to be long?

No. Prompt quality still matters, but length is not the goal. Start with clear business intent, review the generated specification, and use Clarify and Checklist to improve requirement quality before planning and implementation.

## Q&A — What is the productivity claim?

Do not claim a fixed percentage unless the team has measured it.

Use:

> More structured context before coding can reduce clarification and rework loops and make delivery more predictable.
