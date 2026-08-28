# PowerPoint Copilot prompt — redesign the existing screenshot-driven Spec Kit slide

Use this prompt in **PowerPoint Copilot Web with the existing screenshot slide selected**.

The goal is to redesign the selected slide, not create another slide. The current version already contains the three real screenshots, but they are too small in presentation mode. This prompt makes the screenshots the dominant visual content.

---

## Prompt

Redesign the **currently selected slide**. Do **not** create a new slide.

Keep the existing Parametric corporate theme, fonts, colors, footer, confidentiality notice, and overall visual identity.

The objective is to make the **three existing screenshots dramatically larger and readable in presentation mode**.

### Keep this title

**The workflow leaves real, reviewable artifacts**

Remove the current subtitle:

**Real outputs from the Export-to-Excel example**

Remove the explanatory sentences underneath the screenshots.

Remove the large burgundy takeaway banner at the bottom.

Preserve the three-stage story, but make each stage extremely compact:

### 01 — ANALYZE
**Find inconsistencies**

### 02 — TASKS + GATES
**Make work executable**

### 03 — IMPLEMENT
**Act after gates pass**

Place the existing three screenshots immediately below these headings.

---

## Most important layout requirement

The **screenshots must be the dominant visual elements on the slide**.

Increase each screenshot substantially so that the three screenshots together occupy approximately **75–80% of the usable slide area below the main title**.

Use almost all available width and vertical space.

Minimize margins and gaps between the three screenshot panels while maintaining a clean corporate layout.

Do not place paragraphs or bullet points around the screenshots.

Do not shrink the screenshots to make room for explanatory text.

**The screenshots are the explanation.**

Keep subtle arrows between the screenshots to communicate:

**Analyze → Tasks + Gates → Implement**

---

## Do not force equal screenshot dimensions

The screenshots have different natural aspect ratios. Do **not** force all three images into identical boxes.

Use an asymmetric layout that respects their content:

- **Analyze:** approximately 35% of available screenshot width
- **Tasks + Gates:** approximately 27% of available screenshot width
- **Implement:** approximately 38% of available screenshot width

The middle Tasks screenshot can be taller and narrower. The Analyze and Implement screenshots can be wider.

Maintain the original aspect ratios and do not distort the images.

If necessary, crop screenshots rather than scaling the complete screenshots down.

---

## Crop priorities

### Analyze
Prioritize:
- `/speckit.analyze`
- `Specification Analysis Report`
- `No files were modified`
- the findings table showing Severity / Location / Summary / Recommendation

The purpose is to make the read-only consistency check visible.

### Tasks + Gates
Prioritize:
- `Tasks: Export Account Summary`
- prerequisites and readiness status
- Phase 1 and Phase 2 headings
- the first concrete implementation tasks
- visible task IDs, tests, and file paths where readable

The purpose is to show intent becoming concrete, ordered, testable work.

### Implement
Prioritize:
- `/speckit.implement`
- implementation preflight
- prerequisite/checklist checking
- especially the line showing that the **checklist gate passes**
- the transition into repository action

The purpose is to show that Copilot acts only after the approved context and gates are loaded and checked.

---

## Bottom takeaway

Only if there is enough room without reducing screenshot size, add a small single-line takeaway at the bottom:

**Artifacts → Quality Gates → Code**

Do **not** use a large colored banner for this takeaway.

If the takeaway competes with screenshot size, omit it completely.

---

## Desired visual hierarchy

1. **Screenshots — dominant**
2. **Main slide title**
3. **Three short stage labels/headlines**
4. Everything else secondary or removed

Do not add icons, stock imagery, AI illustrations, decorative diagrams, bullet lists, or explanatory paragraphs.

The audience should immediately perceive that these are **real outputs from an actual Spec Kit workflow**, and the important areas of each screenshot should be substantially easier to see from a presentation screen.

---

## Speaker intent

The slide should visually support this short explanation:

> “These are real outputs from the workflow. Analyze catches inconsistencies before coding. Tasks turns the approved design into executable work. Then Implement checks the gates and only then lets the coding agent act.”

The slide should feel like **evidence**, not documentation.
