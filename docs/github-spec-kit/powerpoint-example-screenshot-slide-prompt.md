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

### Title

**The workflow leaves real, reviewable artifacts**

Optional subtitle, only if it does not reduce screenshot size:

**Real outputs from the Export-to-Excel example**

### Critical layout rule

The screenshots must dominate the slide.

Use a clean **three-stage horizontal layout**:

`01 ANALYZE → 02 TASKS + GATES → 03 IMPLEMENT`

Each stage should contain only:

1. stage label
2. one short headline
3. one very large screenshot placeholder
4. one one-line caption

Do **not** add bullet lists.

Do **not** add explanatory paragraphs.

Do **not** add icons, stock imagery, AI illustrations, or decorative diagrams.

Give approximately **65–70% of the usable slide height to the screenshots**.

Make the three screenshot placeholders as large as possible while keeping them equally sized and aligned.

Leave the screenshot areas empty or as simple placeholders so I can insert and crop the real screenshots manually afterward.

---

## STAGE 1 — ANALYZE

Stage label:

**01 — ANALYZE**

Headline:

**Find inconsistencies before coding**

Large screenshot placeholder label:

**Insert screenshot: `/speckit.analyze` report**

One-line caption:

**Cross-checks the artifacts and reports actionable inconsistencies.**

Use the screenshot showing the **Specification Analysis Report table** with severity, file locations, summary, and recommendations.

Do not use the earlier Analyze conversation screenshot if the report-table screenshot is available.

---

## STAGE 2 — TASKS + GATES

Stage label:

**02 — TASKS + GATES**

Headline:

**Turn intent into executable work**

Large screenshot placeholder label:

**Insert screenshot: `Tasks: Export Account Summary`**

One-line caption:

**Creates reviewable tasks and validates readiness before coding.**

Prefer the `Tasks: Export Account Summary` screenshot because it visibly shows phased work, task IDs, prerequisites, tests, and file paths.

The `Specification Quality Checklist` screenshot is a backup option if the tasks screenshot does not crop well.

---

## STAGE 3 — IMPLEMENT

Stage label:

**03 — IMPLEMENT**

Headline:

**Code only after the gates pass**

Large screenshot placeholder label:

**Insert screenshot: `/speckit.implement` preflight**

One-line caption:

**Copilot loads the approved context, checks prerequisites, then acts.**

Use the screenshot showing `/speckit.implement` where Copilot reads the implementation context, checks prerequisites/checklist status, and prepares to edit the repository.

---

## Bottom takeaway

Keep a thin, full-width burgundy takeaway banner at the bottom.

Use:

**Artifacts first. Quality gates next. Code after.**

Do not make the banner tall.

---

## Visual guidance

- The screenshots are the evidence and must be the visual focus.
- Use only minimal labels and captions.
- Keep arrows between the three stages to reinforce progression.
- Keep stage 1 and 3 burgundy accents and stage 2 teal, matching the existing deck.
- Use subtle borders around screenshot placeholders.
- Do not duplicate the detailed five-step workflow from the previous slide.
- This slide should feel like a **visual walkthrough of real Spec Kit outputs**, not a documentation page.
- Leave enough room for manual cropping so the readable part of each screenshot can be enlarged.

---

## Screenshot selection guidance

Use these three screenshots in this order:

1. **Analyze:** the `/speckit.analyze` screenshot with the `Specification Analysis Report` table showing severity, locations, summaries, and recommendations.
2. **Tasks + Gates:** the `Tasks: Export Account Summary` screenshot showing phased tasks, prerequisites, tests, and concrete file paths.
3. **Implement:** the `/speckit.implement` preflight screenshot showing checks of hooks, prerequisites, checklist status, and repository readiness before coding.

Do not use the Constitution screenshot as one of the three primary images on this slide. Constitution is already covered in the conceptual workflow slide.

Do not use both Analyze screenshots; use only the report-table version.

---

## Speaker intent

The slide should make it easy to say:

> “This is the real output of the workflow. Analyze finds inconsistencies. Tasks turn the approved design into reviewable work. Only after the gates pass does Copilot start acting on the codebase.”

The audience should leave understanding that Spec Kit produces **visible, reviewable artifacts and quality gates before code generation**.
