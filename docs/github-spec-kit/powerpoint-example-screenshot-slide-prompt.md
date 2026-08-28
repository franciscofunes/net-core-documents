# PowerPoint Copilot prompt — add a screenshot-driven Spec Kit example slide

Use this prompt in **PowerPoint Copilot Web** to create **one new slide immediately after the existing slide titled `What I actually do in VS Code`**.

The existing `What I actually do in VS Code` slide must remain unchanged. This new slide should complement it with real screenshots from the Export-to-Excel Spec Kit example.

The new slide must be created in the same Parametric corporate template and visual language as the surrounding deck.

---

## Prompt

Create **one new slide** after the currently selected slide.

Do **not** modify the existing slide. Preserve the current Parametric corporate template, footer, confidentiality notice, typography, spacing, burgundy/teal/black color system, and section heading style.

The purpose of the new slide is to show **real evidence from the Spec Kit workflow** using three screenshots from the Export-to-Excel example in the existing financial Angular application.

The previous slide already explains the conceptual flow:

`Specify + Clarify → Plan → Tasks + Gates → Implement → Converge`

This new slide should answer:

**“What did that workflow actually produce in the repository and in Copilot?”**

### Suggested title

**The workflow leaves real, reviewable artifacts**

Suggested subtitle:

**Real outputs from the Export-to-Excel example — analysis, actionable tasks, and implementation readiness.**

### Important layout rule

Create a clean **three-column layout** with three large screenshot placeholders. Each screenshot area should have:

1. a short stage label
2. a short explanatory headline
3. one large rectangular image placeholder
4. no more than 2–3 concise bullets underneath

Do not use decorative AI imagery. The screenshots are the visual evidence.

Leave the image areas empty or as clear placeholders so I can manually insert the screenshots afterward.

---

## COLUMN 1 — ANALYZE

Stage label:

**01 — ANALYZE**

Headline:

**Find inconsistencies before coding**

Use a large screenshot placeholder labeled:

**Insert screenshot: `/speckit.analyze` report**

This screenshot will show the read-only Specification Analysis Report with categories, severity, file locations, summaries, and recommendations.

Use concise bullets:

- Cross-checks specification, plan, research, and tasks
- Identifies missing, duplicated, or inconsistent work before implementation
- Produces findings with severity, exact locations, and recommendations

Small emphasis line if space permits:

**Read-only quality check — no code changed yet**

---

## COLUMN 2 — TASKS + CHECKLIST

Stage label:

**02 — TASKS + GATES**

Headline:

**Turn intent into executable, testable work**

Use a large screenshot placeholder labeled:

**Insert screenshot: `tasks.md` or specification quality checklist**

This screenshot will show either:

- `Tasks: Export Account Summary` with phased task IDs and prerequisites, or
- `Specification Quality Checklist: Export Account Summary`

Use concise bullets:

- Tasks are ordered by dependency and tied to concrete files/tests
- Checklist validates completeness, ambiguity, success criteria, and scope
- The Constitution can require test-first behavior before implementation

Small emphasis line if space permits:

**The workflow produces artifacts that can be reviewed before Copilot writes code**

---

## COLUMN 3 — IMPLEMENTATION READY

Stage label:

**03 — IMPLEMENT**

Headline:

**Copilot acts only after the gates pass**

Use a large screenshot placeholder labeled:

**Insert screenshot: `/speckit.implement` preflight**

This screenshot will show Copilot reading the implementation prompt, checking hooks/prerequisites/checklist state, and confirming the implementation preflight before editing the codebase.

Use concise bullets:

- Loads the approved feature context and task plan
- Checks prerequisites and checklist status before coding
- Then uses normal coding-agent tools: search, read, edit, terminal, tests

Small emphasis line if space permits:

**This is where the agent moves from planning context to action**

---

## Bottom takeaway banner

Add one strong full-width burgundy takeaway banner at the bottom, matching the style of the existing slides.

Use this message:

**Spec Kit makes the reasoning visible: analyze the artifacts → validate the work → then let the coding agent implement.**

Alternative shorter version if space is tight:

**Artifacts first. Quality gates next. Code after.**

---

## Visual guidance

- Keep this slide visually lighter than a documentation page.
- The three screenshots should occupy most of the slide area.
- Avoid long paragraphs.
- Keep each column visually balanced.
- Use burgundy for stage 1 and 3 accents and teal for stage 2, consistent with the surrounding slides.
- Use thin separators or subtle borders around screenshot placeholders.
- Make the three-stage progression clearly read left to right.
- Do not duplicate the detailed five-step workflow from the previous slide.
- This slide should feel like **evidence / proof of the workflow**, not another theory slide.

---

## Screenshot selection guidance

When I manually add the images, use these three screenshots in this order:

1. **Analyze:** the screenshot showing `/speckit.analyze` and the `Specification Analysis Report` table with severity, locations, summary, and recommendations.
2. **Tasks + Gates:** the screenshot showing either `Tasks: Export Account Summary` or `Specification Quality Checklist: Export Account Summary`. Prefer the tasks screenshot if only one can be used because it shows concrete phased implementation work and test requirements.
3. **Implement:** the screenshot showing `/speckit.implement` preflight where Copilot checks hooks, prerequisites, checklist status, and then prepares to edit the repository.

Do not use the Constitution screenshot as one of the three primary images on this slide. The Constitution is already explained conceptually in the previous workflow slide and is less useful as visual evidence of the feature execution path.

Do not use both Analyze screenshots; select the one with the report table because it communicates value faster to the audience.

---

## Speaker intent for this slide

The slide should make it easy for the presenter to say:

> “This is what I mean by context and workflow rather than one giant prompt. Analyze gives me a structured consistency report. Tasks and checklists turn the agreed specification into reviewable, testable work. Only after those gates pass does Copilot move into implementation and start acting on the codebase.”

The audience should leave this slide understanding that Spec Kit produces **persistent, reviewable artifacts and explicit quality gates before code generation**.
