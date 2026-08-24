# GitHub Copilot integration and the Skills path

## The important distinction

Spec Kit is not GitHub Copilot and it is not itself a single coding agent.

A clean mental model is:

```text
GitHub Copilot = coding-agent environment
Spec Kit = SDD toolkit / extensible harness
Spec Kit Skills = specialized capabilities exposed to the agent
Copilot tools = read, search, edit, terminal, tests, etc.
Repository artifacts = persistent context between stages
```

## What `specify init` does

Spec Kit supports many AI coding-agent integrations. The integration layer scaffolds the command files and directory structure expected by the selected agent environment.

For GitHub Copilot, the current official integration reference says:

- key: `copilot`
- **Skills-based by default**
- installs `speckit-<command>/SKILL.md` under `.github/skills/`
- a supported commands layout can be requested with `--integration-options="--commands"`
- that commands layout uses `.agent.md` files under `.github/agents/`, companion `.prompt.md` files under `.github/prompts/`, plus VS Code settings integration

This explains why a developer may see both concepts in Copilot-based environments or in repositories that were migrated/upgraded over time: Skills and custom-agent/prompt representations are different integration mechanisms for exposing Spec Kit behavior.

## Presentation recommendation

For a forward-looking and simple demo, focus on the **Skills path**.

Use this message:

> I stay in GitHub Copilot Chat in Agent mode, and invoke specialized Spec Kit capabilities for each SDD stage.

Conceptually:

```text
VS Code
  -> GitHub Copilot Chat
      -> Agent mode
          -> /speckit-specify
          -> /speckit-clarify
          -> /speckit-plan
          -> /speckit-checklist
          -> /speckit-tasks
          -> /speckit-analyze
          -> /speckit-implement
          -> /speckit-converge
```

Exact invocation syntax can vary by integration and version. The official reference often documents commands as `/speckit.*`, while skills-based integrations may expose hyphenated forms. The presentation should match the UI actually visible in the demo repository.

## Agent selector vs Skill

Do not conflate these terms:

### Agent / Agent mode

The coding agent is the entity that reasons, chooses actions, and uses tools.

### Skill

A Skill is a packaged capability/instruction set that teaches or guides the coding agent for a specific job.

### Model

The model is the underlying LLM powering the agent.

### Tools

Tools are actionable capabilities available to the agent, such as reading the workspace, searching code, editing files, invoking a shell, or running tests.

A useful line:

> The agent is doing the work; the skill tells the agent how to perform a particular Spec Kit stage.

## Are many Spec Kit agents talking to each other?

Not in the standard mental model for the Skills flow.

A safer explanation is:

```text
              Copilot coding agent
                      |
          +-----------+-----------+
          |                       |
    Spec Kit Skills           Copilot tools
          |                       |
          +-----------+-----------+
                      |
             repository context
          constitution / spec / plan
             tasks / source code
```

The stages primarily communicate through durable repository artifacts rather than through a chain of independent agents chatting with one another.

## Sources

- https://github.com/github/spec-kit/blob/main/docs/reference/integrations.md
- https://github.com/github/spec-kit/blob/main/docs/reference/agentic-sdd.md
- https://github.com/github/spec-kit/blob/main/README.md
