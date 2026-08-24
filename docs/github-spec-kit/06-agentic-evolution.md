# How Spec Kit can evolve toward more agentic workflows

## Start with the standard SDD mental model

The standard Spec Kit SDD flow does **not** require a group of independent agents talking to one another.

A safer model is:

```text
Human
  -> Copilot coding agent
      -> Spec Kit capability
          -> repository artifacts
              -> next capability
```

The stages share durable artifacts such as the Constitution, `spec.md`, `plan.md`, `tasks.md`, checklists, and the codebase.

## Why it is still agentic

The official reference describes the `/speckit.*` sequence as an **agentic process** that the coding agent runs step by step.

The agent can reason over context, invoke tools, edit code, run commands/tests, and iterate through verification.

A useful conceptual formula is:

> Agentic Development = Model + Context + Tools + Workflow + Feedback

## Beyond the core SDD commands

The current Spec Kit reference exposes additional primitives that make the toolkit broader than a linear set of slash commands.

### Extensions

Extensions add capabilities beyond the built-in SDD process, for example:

- domain-specific commands
- external tool integrations
- quality gates
- additional templates
- before/after command hooks

Project-level extension registration and hooks can live in `.specify/extensions.yml`.

This makes it possible to add organization-specific checks around implementation without changing the core SDD process.

### Presets

Presets customize existing Spec Kit behavior by overriding commands, templates, and scripts. They can be stacked with priority ordering.

Useful conceptually for:

- organization standards
- methodology customization
- localization
- consistent team conventions

### Workflows

Workflows automate multi-step SDD processes.

The official workflow reference supports:

- command steps
- prompt steps
- shell steps
- human checkpoints / gates
- conditional logic
- loops
- fan-out / fan-in
- pause and resume from the interrupted step

This is where Spec Kit clearly moves from a developer manually invoking each stage toward larger workflow orchestration.

### Bundles

Bundles package extensions, presets, workflows, and steps into a versioned installable unit for a role or team.

They are useful for distributing a governed setup rather than asking every developer to assemble the process manually.

## Example: more automated financial-app flow

```text
Jira feature
   |
   v
Specify
   |
Clarify
   |
Plan
   |
Tasks
   |
Compliance / architecture gate       <- extension or workflow gate
   |
Implement
   |
Run tests / static checks             <- workflow shell/tool steps
   |
Automated review                      <- extension / agentic step
   |
Converge
   |
Human approval                        <- workflow checkpoint
```

## Multi-agent possibility

Do not claim that Spec Kit's default SDD pipeline is inherently multi-agent.

A more accurate Q&A answer:

> The default workflow can run with one coding agent using shared repository context. Spec Kit's extensibility and workflow orchestration can support more automated processes and can be combined with environments that delegate work to specialized/sub-agents when that is useful.

The key architectural point is that **persistent artifacts remain a coordination layer** even when orchestration becomes more sophisticated.

## Sources

- https://github.com/github/spec-kit/blob/main/docs/reference/overview.md
- https://github.com/github/spec-kit/blob/main/docs/reference/extensions.md
- https://github.com/github/spec-kit/blob/main/docs/reference/workflows.md
- https://github.com/github/spec-kit/blob/main/docs/reference/agentic-sdd.md
