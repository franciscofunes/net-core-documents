# PowerPoint Copilot prompts — improve the 3-slide Spec Kit presentation

These prompts are designed to be pasted **one slide at a time** into PowerPoint Copilot Web while the corresponding slide is selected.

The goal is to improve the existing slide, **not create a different presentation**. Preserve the Parametric corporate template, footer, confidentiality notice, slide section heading (`05 | Frontend Development`), and the existing burgundy/teal/black visual language.

General rules for all three slides:

- Keep the presentation suitable for a mixed technical/non-technical audience.
- Keep the three-slide story understandable in approximately five minutes.
- Prefer diagrams, hierarchy, whitespace, arrows, and short labels over paragraphs.
- Do not add generic AI robot imagery, stock photos, or decorative illustrations.
- Do not invent quantitative productivity claims.
- Do not change the core GitHub Spec Kit terminology.
- Do not imply that the default Spec Kit workflow is multiple autonomous agents communicating with each other.
- GitHub Copilot should be presented as the coding agent; Spec Kit provides structured SDD capabilities, artifacts, context, gates, and verification around it.
- Preserve enough detail for the speaker to explain the workflow, but do not turn the slide into documentation.

---

## Prompt 1 — Improve Slide 1: What Spec-Driven Development changes

Improve the currently selected slide while preserving the existing Parametric corporate template, footer, typography hierarchy, burgundy/teal palette, and the heading `05 | Frontend Development`.

The purpose of this slide is to explain the **power inversion** behind GitHub Spec Kit / Spec-Driven Development in less than 75 seconds.

### Most important correction

The current traditional-development diagram can visually imply `CODE → requirements + design`, which is backwards as a development sequence.

Redesign that comparison so the meaning is immediately clear:

**Traditional development**

`requirements + design → implementation/code`

Then visually emphasize that **CODE becomes the source of truth**, while supporting requirements/design documentation can drift out of date.

Contrast it with:

**Spec-Driven Development**

`INTENT (what + why) → spec.md → plan.md → IMPLEMENTATION`

Where:

- `spec.md` = WHAT + WHY
- functional requirements
- user scenarios
- success criteria
- technology-agnostic business behavior

And:

- `plan.md` = HOW
- technology stack
- architecture
- dependencies
- implementation decisions

### Visual hierarchy

Make the traditional path visually simpler and slightly de-emphasized.

Make the Spec-Driven path the visual focus of the slide.

The eye should naturally move left-to-right through:

`Intent → spec.md → plan.md → Implementation`

Keep the existing concept that the developer starts with intent — the **what and why** — before deciding the **how**.

### Bottom takeaway

Keep a strong full-width takeaway banner, but make it concise and presentation-friendly:

**From one-shot prompting to engineered context and workflow around the coding agent.**

Do not say that prompt engineering is dead.

The intended message is:

**Prompt quality still matters, but the prompt is no longer responsible for carrying all the context.**

Do not add repository folder details to this slide; those concepts will be explained verbally and reinforced on the workflow slide.

---

## Prompt 2 — Improve Slide 2: The complete Spec Kit flow

Improve the currently selected slide while preserving the Parametric corporate template, footer, heading, burgundy/teal/black visual system, and the current overall concept.

This should remain the **main conceptual workflow slide**.

The slide must clearly distinguish **project-level foundation** from the **feature-level lifecycle**.

### Project level

Keep `CONSTITUTION` above the feature flow and visually separate it from the numbered feature steps.

Use concise wording such as:

**CONSTITUTION — created once and merged to main; persistent project principles every feature must respect.**

Do not make Constitution look like something the developer repeats for every feature.

### Feature level

Keep the excellent four-group structure and make it even easier to scan:

**DEFINE**
1. Specify
2. Clarify

**DESIGN**
3. Plan
4. Checklist

**DELIVER**
5. Tasks
6. Analyze
7. Implement

**VERIFY**
8. Converge
9. Refine / repeat when gaps remain

Use short explanatory phrases rather than paragraphs.

Suggested wording:

**Specify** — create the business specification (`spec.md`)

**Clarify** — remove ambiguity and write decisions back into the spec

**Plan** — map requirements to technology and architecture (`plan.md`)

**Checklist** — review requirement quality; think “unit tests for requirements”

**Tasks** — generate dependency-ordered executable work (`tasks.md`)

**Analyze** — cross-check consistency across spec, plan, and tasks

**Implement** — execute the approved tasks

**Converge** — compare actual code against the artifacts

### Context-engineering layer

Without overcrowding the slide, add a subtle visual cue showing that the workflow is connected by **persistent repository context**, not isolated prompts.

For example, use a thin secondary line or small label beneath the four groups:

`constitution.md  •  spec.md  •  plan.md  •  tasks.md  •  checklists  •  existing codebase`

Label this subtly as:

**Persistent repository context**

Do not create a separate large folder tree.

### Verification loop

Keep the bottom feedback-loop banner and make the loop visually obvious:

`Gap found → append/refine tasks → implement again → converge again`

The audience should understand that Converge is not simply “the end”; it can send work back into the cycle until code and artifacts align.

### Key message

The slide should communicate visually:

**This is not just a sequence of slash commands. It is a structured workflow with refinement, quality gates, persistent context, and feedback.**

---

## Prompt 3 — Improve Slide 3: What I actually do in VS Code

Improve the currently selected slide while preserving the Parametric corporate template, footer, heading, and existing burgundy/teal/black styling.

This is the **practical demonstration slide** and should feel more concrete than Slide 2.

The scenario is a brownfield financial Angular application.

### Jira requirement

Keep the feature prominent at the top:

**Add Export to Excel to the Reporting Dashboard**

Keep the three important business constraints visible and concise:

- respect active dashboard filters
- export every matching reporting row
- not only the currently visible page

### Developer environment

Make this relationship visually explicit near the top of the workflow:

**VS Code + GitHub Copilot Chat — Agent mode**

Then underneath:

**Copilot = coding agent**

**Spec Kit = structured SDD skills/workflow + persistent artifacts + quality/verification**

Do not portray Specify, Plan, Tasks, Implement, etc. as independent agents talking to one another.

### Practical workflow

Keep the existing five-block practical sequence because it is easier to understand than repeating all eight conceptual steps from Slide 2:

**01 — SPECIFY + CLARIFY**

Start with enough business intent, not a giant perfect prompt. Review `spec.md`, then resolve ambiguity around columns, permissions, scale, loading, errors, and export behavior.

**02 — PLAN**

Make the brownfield aspect especially prominent.

The coding agent investigates the existing application:

- Reporting Dashboard
- filter state
- Angular components/services
- API patterns
- authorization
- existing export utilities
- tests
- architecture

Use a concise line such as:

**Fit the feature into the architecture we already have — do not invent a new one.**

**03 — TASKS + GATES**

Turn the approved plan into dependency-ordered work. Checklist and Analyze catch gaps before coding.

**04 — IMPLEMENT**

Show that Copilot now acts using development tools:

`search • read • edit • terminal • tests`

This is important because it distinguishes the coding agent from Spec Kit itself.

**05 — CONVERGE**

Compare implementation with the specification, plan, and tasks. If a gap remains, create/refine work and repeat the loop.

### Context progression

If space permits, add a very subtle secondary visual below the five steps showing how context accumulates:

`Jira intent → spec.md → plan.md → tasks.md → code → verification`

This should reinforce that each phase leaves durable context for the next phase.

### Bottom key message

Keep the existing bottom banner and preserve this message almost exactly:

**We do not jump from Jira to generated code — we progressively build and verify context before implementation.**

This is the strongest takeaway of the practical slide.

Do not add quantitative time-savings.

If a productivity statement is needed, use only:

**More structured context before coding can reduce clarification and rework loops and make delivery more predictable.**

---

# Optional final consistency prompt

After improving all three slides individually, select the three slides and ask PowerPoint Copilot:

Review these three slides as one five-minute story about GitHub Spec Kit and Spec-Driven Development.

Do not redesign them from scratch. Preserve the Parametric corporate template and existing visual language.

Check only for consistency and presentation quality:

1. Slide 1 should answer **WHY Spec-Driven Development?**
2. Slide 2 should answer **HOW does the complete Spec Kit workflow work?**
3. Slide 3 should answer **WHAT does the developer actually do in VS Code on a brownfield Angular feature?**

Ensure terminology, colors, arrows, capitalization, spacing, and hierarchy are consistent across all three slides.

Remove redundant sentences where one slide repeats another.

Keep `spec.md = WHAT + WHY` and `plan.md = HOW` consistent everywhere.

Keep Constitution clearly project-level and already established before the feature workflow.

Keep GitHub Copilot as the coding agent and Spec Kit as the structured SDD workflow/context layer around it.

Make the progression feel intentional:

`Why → Workflow → Real developer experience`

Do not introduce new concepts, claims, statistics, or extra slides.
