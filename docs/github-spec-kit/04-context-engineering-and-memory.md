# Context engineering, memory, and agent context

## Why Spec Kit fits the context-engineering conversation

Prompt engineering asks:

> How do I write the best instruction?

Context engineering asks:

> What information does the model need, when does it need it, and how do we keep that context relevant and persistent?

Agentic software development adds another layer:

> How does an agent use that context, tools, workflow, and feedback to accomplish a larger development goal?

Spec Kit is useful in this framing because the initial prompt is only one source of information.

## The prompt is not carrying everything

For a feature, the coding agent can work from several context layers:

```text
Human intent
  Jira / prompt
      |
      v
Project context
  constitution.md
      |
      v
Feature context
  spec.md
  plan.md
  tasks.md
  checklists
      |
      v
Code context
  existing repository
  architecture
  dependencies
  tests
      |
      v
Coding agent
```

A useful presentation line:

> The prompt still matters, but it is no longer responsible for carrying all the context.

## What “memory” means here

Do not confuse Spec Kit repository memory with conversational LLM memory.

### Project-level persistent context

The DeepWiki SDD material describes the project Constitution under `.specify/memory/constitution.md` as permanent project context for the coding agent.

That is better described in a talk as **persistent project context** rather than magical AI memory.

### Feature-level persistent context

Each feature evolves through durable artifacts such as:

- `spec.md`
- `plan.md`
- `tasks.md`
- requirement/custom checklists

These files survive across chat turns, editor restarts, and developer handoffs because they live in the repository.

The artifacts are also the primary communication mechanism between SDD stages.

## Agent Context Management

Current Spec Kit includes an opt-in `agent-context` extension.

Its `speckit.agent-context.update` command refreshes a managed Spec Kit section inside the active coding agent's instruction/context file. Examples in the upstream source include:

- `CLAUDE.md`
- `.github/copilot-instructions.md`
- `AGENTS.md`

The extension reads configuration from:

```text
.specify/extensions/agent-context/agent-context-config.yml
```

It can manage one or multiple project-relative context files. Managed blocks use markers such as:

```text
<!-- SPECKIT START -->
...
<!-- SPECKIT END -->
```

The update logic can point the managed section at the most recent `plan.md` discovered under `specs/`.

This is important because Spec Kit is not only a set of slash commands. It can also maintain agent-facing context that points the coding agent toward the current project/feature artifacts.

## Presentation-safe synthesis

```text
                 CODING AGENT
                      ^
                      |
             ENGINEERED CONTEXT
                      |
       +--------------+--------------+
       |              |              |
Project context  Feature context   Code context
constitution      spec.md          existing repo
                  plan.md          architecture
                  tasks.md         dependencies/tests
       |              |              |
       +--------------+--------------+
                      ^
                      |
                Human intent
                 Jira + prompt
```

## Agentic development formula

A useful conceptual formula for the talk:

> Agentic Development = Model + Context + Tools + Workflow + Feedback

GitHub Copilot provides the coding-agent environment, model access, and development tools. Spec Kit primarily structures intent, context, workflow, persistent artifacts, quality gates, and feedback loops.

## Sources

- https://github.com/github/spec-kit/blob/main/extensions/agent-context/commands/speckit.agent-context.update.md
- https://github.com/github/spec-kit/blob/main/docs/reference/agentic-sdd.md
- DeepWiki PDF: *Spec-Driven Development | github/spec-kit*.
