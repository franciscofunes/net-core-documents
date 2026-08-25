# Five-minute presentation guion

This is the read-aloud version for the presentation. Keep the pace conversational. The goal is to explain the workflow clearly, not to read every label that appears on the slides.

## Slide 1 — What Spec-Driven Development changes (~1 minute)

GitHub Spec Kit implements what GitHub calls Spec-Driven Development.

The main idea is a power inversion.

Traditionally, we start with requirements or design documents, then we implement, and eventually the code becomes the real source of truth. The problem is that the original documentation can become outdated.

With Spec-Driven Development, we try to reverse that relationship. The specification and the implementation plan become durable artifacts that guide the code.

The developer starts by expressing the **what and why**, before deciding the **how**.

That distinction is important. `spec.md` contains the functional requirements, user scenarios and success criteria. It should describe what we want the system to do.

Then `plan.md` contains the technical implementation: architecture, technologies, dependencies and design decisions.

This is also why I see Spec Kit as closer to **context engineering** than traditional prompt engineering. The prompt still matters, but the prompt is no longer responsible for carrying all of the context.

The focus shifts from crafting one perfect prompt to engineering the context and workflow around the coding agent.

## Slide 2 — The complete Spec Kit workflow (~1 minute 20 seconds)

At project level we start with the **Constitution**.

In our case, that part is already done and merged into `main`. We do not recreate the Constitution for every feature. It provides permanent project principles and constraints that later work should respect.

For a new feature, we start with **Specify**. We give the system a natural-language description of the feature and it creates the first specification.

Then we have **Clarify**. This is important because the first specification does not need to be perfect. Clarify helps detect ambiguity, asks targeted questions, and folds those answers back into the specification.

After that comes **Plan**. This is where the technical implementation enters. The agent maps the business requirements to the real application architecture, technologies and dependencies. There is also a Constitution check here.

Then we have **Checklist** and **Tasks**. Checklist helps review requirement quality, while Tasks converts the plan into dependency-ordered executable work.

**Analyze** can then check consistency between the specification, plan and tasks before implementation.

Then **Implement** executes those tasks.

Finally, **Converge** compares the actual code against the specification and plan. If something is missing, it can add new tasks and we go through the loop again.

So the important point is that this is not simply a linear list of prompts. There are refinement steps, quality gates and a verification loop.

## Slide 3 — What I actually do in VS Code (~1 minute 40 seconds)

Now let's make this practical.

Imagine I receive a Jira ticket for our existing financial Angular application.

The requirement is: add **Export to Excel** to the Reporting Dashboard table.

The export should respect the active dashboard filters and export all matching reporting rows, not only the rows currently visible on the page.

I open the solution in Visual Studio Code and use GitHub Copilot Chat in Agent mode.

For this example, Copilot is the coding agent and Spec Kit provides the structured capabilities around it.

I start with `speckit-specify`.

I do not need to write a giant perfect prompt. I need enough business intent to create a useful first specification.

Then I read `spec.md`.

If something is unclear, I run Clarify. For example: which columns should be exported? Does it export the current page or every filtered result? Are there permissions? What happens with very large datasets? What should happen if the export fails?

Once the business behavior is clear, I run Plan.

This is especially important in a brownfield application. The agent now investigates the existing Angular code: the Reporting Dashboard component, filters, services, API patterns, authorization, testing conventions and any existing export utilities.

The goal is not to invent a brand-new architecture. The goal is to make the feature fit the existing application.

Then Tasks converts the approved plan into executable work.

After the quality checks, Implement allows Copilot to use its normal tools: search files, read code, edit files, run terminal commands and execute tests.

And finally Converge verifies that what we implemented actually matches the intent.

The sentence I would emphasize here is:

> **We do not jump directly from Jira to generated code.**

We progressively create, refine and verify the context before implementation.

## Slide 4 — Repository structure and context engineering (~1 minute)

This slide explains where all this context actually lives.

Spec Kit is not relying only on the current Copilot chat conversation.

At project level we have persistent context such as the Constitution.

At feature level we have artifacts such as `spec.md`, `plan.md`, `tasks.md` and checklists.

We also have the existing application code itself, which is extremely important in a brownfield project.

Spec Kit also includes scripts and agent-context mechanisms that help keep the coding agent informed about relevant project state, such as the active feature, technology stack and current implementation context.

So instead of thinking that one prompt contains everything the AI needs, we have multiple sources of engineered context.

The human provides the intent.

The repository provides project principles and existing code.

The feature artifacts provide specification, plan and tasks.

The coding agent has tools to read, search, modify and test the application.

And the workflow provides the feedback loop.

A simple way I like to summarize it is:

> **Agentic Development = Model + Context + Tools + Workflow + Feedback.**

GitHub Copilot gives us the coding-agent environment and tools. Spec Kit structures much of the context, workflow and verification around that agent.

## Closing (~15 seconds)

So the main takeaway is that Spec Kit is not about replacing developers with a better prompt.

It gives us a structured way to move from business intent to implementation while keeping requirements, technical decisions, tasks and code connected.

And that is why I see it as a practical example of the move from simple prompt engineering toward context engineering and more agentic software-development workflows.

## Q&A — Is this multi-agent?

Not by default. The simpler model is one coding agent using different Spec Kit capabilities and shared repository artifacts.

Spec Kit can later become more automated through extensions, presets, workflows and bundles, including more sophisticated orchestration.

## Q&A — Does the first prompt need to be long?

No. Prompt quality still matters, but length is not the goal. Start with clear business intent, review the generated specification, and use Clarify and Checklist to improve requirement quality before planning and implementation.

## Q&A — What is the productivity claim?

Do not claim a fixed percentage unless the team has measured it.

Use:

> More structured context before coding can reduce clarification and rework loops and make delivery more predictable.
