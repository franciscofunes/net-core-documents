# PowerPoint Copilot prompt

Use the following as a self-contained prompt in an isolated PowerPoint Copilot environment.

---

Create a professional presentation about GitHub Spec Kit and Spec-Driven Development (SDD).

## Audience and length

Audience: software developers and technical stakeholders who may not know Spec Kit.

Length: approximately five minutes.

Create 3 or 4 slides maximum. Prefer diagrams and simple flows over dense paragraphs. Put detailed explanation in speaker notes.

## Scenario

We have an existing brownfield financial application built with Angular.

A Jira ticket asks:

"Add Export to Excel to the Reporting Dashboard table."

The export should respect active dashboard filters, export all matching reporting rows rather than only the visible page, preserve the expected reporting columns, and follow the application's existing permissions, UX, architecture, service, and testing patterns.

The project is already initialized with GitHub Spec Kit. The project Constitution has already been created and merged to `main`.

## Slide 1 — What Spec-Driven Development changes

Title: **GitHub Spec Kit: From Prompting to Spec-Driven Development**

Explain the SDD "power inversion":

Traditional development:
requirements / design docs -> implementation -> code becomes the real source of truth.

Spec-Driven Development:
intent -> specification -> plan -> implementation, with code serving the specification.

Highlight:

- specifications as executable assets
- intent-driven development: WHAT and WHY first
- single source of truth

Show the critical separation:

`spec.md` = WHAT / WHY = functional requirements, user scenarios, success criteria, technology agnostic.

`plan.md` = HOW = tech stack, architecture, dependencies, implementation details.

Speaker note:
Do not say "prompt engineering is dead." Say: **"The prompt is no longer responsible for carrying all the context."** Explain that Spec Kit aligns well with context engineering because context also comes from the Constitution, spec, plan, tasks, checklists, existing codebase, and agent context.

## Slide 2 — Complete Spec Kit feature flow

Title: **From Business Intent to Verified Implementation**

Show the project Constitution above the feature workflow with a badge: **Already established and merged to main**.

Then show:

Jira / business intent
-> Specify -> `spec.md`
-> Clarify -> updated `spec.md`
-> Plan -> `plan.md`
-> Checklist / requirements-quality gate
-> Tasks -> `tasks.md`
-> Analyze -> cross-artifact consistency
-> Implement -> working code
-> Converge -> verified implementation

Show Converge as a loop:

Converge -> gaps? -> append tasks -> Implement again -> Converge again until converged.

Explain that Constitution, Specify, Plan, Tasks, Implement are the main SDD phases; Clarify, Checklist, Analyze, and Converge provide refinement, quality gates, consistency checks, and verification.

Use these details in speaker notes:

- Clarify asks targeted questions and writes answers back into the specification.
- Checklist is requirements-quality review, conceptually "unit tests for requirements."
- Tasks are dependency ordered and organized into Setup, Foundational work, user-story phases, and polish/cross-cutting work.
- Analyze is read-only and checks `spec.md`, `plan.md`, and `tasks.md` for conflicts or missing coverage.
- Implement executes tasks and reads checklist state before proceeding.
- Converge compares the codebase against spec, plan, and tasks and appends missing tasks when necessary.

## Slide 3 — What the developer actually does

Title: **Developer Experience: Jira -> Copilot -> Angular**

Make this look like a practical VS Code / GitHub Copilot Chat workflow.

Use the brownfield Jira example: Export to Excel from the financial Reporting Dashboard.

Show:

VS Code
-> GitHub Copilot Chat
-> Agent mode
-> Spec Kit Skills / capabilities

Then the practical sequence:

Specify
-> review `spec.md`
-> Clarify
-> review updated spec
-> Plan
-> review `plan.md`
-> Checklist / Tasks
-> Analyze
-> Implement
-> Converge

In the Plan step, visually show the agent inspecting the existing Angular application:

- Reporting Dashboard components
- current filter state
- services and APIs
- permissions
- existing export/download utilities
- tests
- architecture and dependency conventions

Speaker note:
Do not describe this as many Spec Kit agents automatically talking to one another. Use this mental model:

GitHub Copilot = coding agent.

Spec Kit Skills/workflow = specialized capabilities guiding the agent.

Repository artifacts = persistent context and communication between stages.

The first prompt does not need to be enormous. Start with clear business intent, review the generated specification, and progressively improve context through Clarify, Checklist, Plan, Tasks, Analyze, and Converge.

## Optional Slide 4 — Context engineering and repository structure

Title: **Why This Is More Than Prompt Engineering**

Show a simplified tree:

```text
financial-angular-app/
|-- .github/
|   `-- skills/
|       |-- speckit-specify/SKILL.md
|       |-- speckit-plan/SKILL.md
|       |-- speckit-tasks/SKILL.md
|       `-- ...
|-- .specify/
|   |-- memory/constitution.md
|   |-- extensions/
|   `-- workflows/
|-- specs/
|   `-- NNN-export-reporting/
|       |-- spec.md
|       |-- plan.md
|       |-- tasks.md
|       `-- checklists/
`-- src/app/
    `-- existing Angular application
```

Explain:

`.github/skills` = coding-agent capabilities/instructions.

`.specify` = project-level Spec Kit context, state, extensions, workflow infrastructure.

`specs/<feature>` = durable feature context.

`src/app` = brownfield application being changed.

Mention that current Spec Kit also has an optional Agent Context extension capable of maintaining managed Spec Kit sections in agent instruction files such as `.github/copilot-instructions.md`, `AGENTS.md`, or other configured context files.

Use this synthesis:

**Agentic Development = Model + Context + Tools + Workflow + Feedback**

GitHub Copilot provides the coding-agent environment and development tools. Spec Kit structures much of the intent, context, workflow, quality gates, and verification loop.

## Advanced Q&A only

If asked how SDD can become more agentic, mention:

- Extensions add capabilities, integrations, hooks, and quality gates.
- Presets customize commands, templates, and scripts.
- Workflows automate multi-step processes with conditions, loops, shell steps, human checkpoints, fan-out/fan-in, and pause/resume.
- Bundles package extensions, presets, workflows, and steps for a team or role.

Do not claim the default Spec Kit flow is inherently multi-agent. Say that it works with a coding agent using shared repository context, while extensibility and workflow orchestration can support more sophisticated automated or delegated agentic processes.

## Design requirements

Use a modern GitHub/developer aesthetic: dark navy, white, neutral grays, blue accents, green for verified/converged states, and orange for planning or quality gates.

Avoid generic robot imagery and stock photos. Prefer workflow diagrams, artifact/file cards, a VS Code/Copilot-like interaction panel, repository trees, and arrows.

Do not invent quantitative time savings. Use this productivity message:

**More structured context before coding can reduce clarification and rework loops and make delivery more predictable.**

---

## Source basis

The prompt above was synthesized from the research in this folder and checked against the current `github/spec-kit` repository, especially:

- `README.md`
- `docs/reference/agentic-sdd.md`
- `docs/reference/integrations.md`
- `docs/reference/overview.md`
- `docs/reference/extensions.md`
- `docs/reference/workflows.md`
- `extensions/agent-context/commands/speckit.agent-context.update.md`
