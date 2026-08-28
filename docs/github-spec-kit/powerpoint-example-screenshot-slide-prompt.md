# PowerPoint Copilot prompt — edit the existing Spec Kit screenshot slide in place

Use this prompt in **PowerPoint Copilot Web with the existing screenshot slide selected**.

This is an **EDIT-IN-PLACE prompt**. It must modify the selected slide only. It must **not create a new slide, duplicate the slide, replace the slide with a new layout, or delete and recreate any screenshot**.

The current slide already contains the correct three screenshots and the correct three-stage sequence. The only goal is to make those existing screenshots much larger and easier to read in presentation mode.

---

## Prompt

Edit the **currently selected slide in place**.

**Do not create a new slide. Do not duplicate this slide. Do not remove and recreate the slide. Do not replace the three existing screenshots. Reuse the objects already on this slide and only resize, crop, move, and simplify them.**

Keep the existing Parametric corporate theme, fonts, colors, footer, confidentiality notice, and overall visual identity.

Keep the existing three screenshots in the same order:

**01 — ANALYZE → 02 — TASKS + GATES → 03 — IMPLEMENT**

The objective is to make the **existing screenshots dramatically larger and readable in presentation mode**.

### Keep the title

**The workflow leaves real, reviewable artifacts**

### Remove or reduce existing text to create space

Remove the current subtitle:

**Real outputs from the Export-to-Excel example**

Remove the explanatory sentences underneath the screenshots.

Remove the large burgundy takeaway banner at the bottom.

Shorten the three headings to:

**01 — ANALYZE**  
*Find inconsistencies*

**02 — TASKS + GATES**  
*Make work executable*

**03 — IMPLEMENT**  
*Act after gates pass*

Do not add new paragraphs, bullets, or captions.

---

## Resize the existing screenshot objects

Use the existing screenshots already on the slide. **Do not replace them with placeholders or new images.**

Resize and reposition them so that the screenshots together occupy approximately **75–80% of the usable slide area below the title**.

Use almost all available width and vertical space.

Minimize margins and gaps between the screenshot areas while keeping a clean corporate layout.

Keep subtle arrows between the three stages if they still fit without reducing screenshot size.

The screenshots are the explanation.

---

## Preserve each screenshot's natural shape

Do not force all three existing images into identical dimensions.

Use an asymmetric layout that better fits their current aspect ratios:

- **Analyze:** approximately 35% of available screenshot width
- **Tasks + Gates:** approximately 27% of available screenshot width
- **Implement:** approximately 38% of available screenshot width

The middle Tasks screenshot can remain taller and narrower. The Analyze and Implement screenshots can be wider.

Do not distort the images.

---

## Crop the existing images only when needed

If more readability is needed, crop the **existing screenshot objects in place** instead of shrinking the entire images.

### Analyze — existing left image
Prioritize keeping visible:
- `/speckit.analyze`
- `Specification Analysis Report`
- `No files were modified`
- the first findings rows with Severity / Location / Summary / Recommendation

### Tasks + Gates — existing center image
Prioritize keeping visible:
- `Tasks: Export Account Summary`
- prerequisites / readiness status
- Phase 1 and Phase 2 headings
- the first concrete implementation tasks

### Implement — existing right image
Prioritize keeping visible:
- `/speckit.implement`
- implementation preflight text
- prerequisite/checklist checking
- especially the line where the **checklist gate passes**

Do not delete these screenshots and do not ask me to insert them again.

---

## Bottom area

If space remains after enlarging the screenshots, add only a small single-line text at the bottom:

**Artifacts → Quality Gates → Code**

Do not use a large banner.

If this text would reduce screenshot size, omit it.

---

## Final constraint

This must remain the **same selected slide with the same three screenshot objects**.

Allowed actions:
- resize
- crop
- move
- align
- shorten/remove text
- reduce spacing

Not allowed:
- create a new slide
- duplicate the slide
- replace the slide
- delete/reinsert screenshots
- create screenshot placeholders
- introduce new graphics or imagery

The final result should feel like **three large pieces of evidence** rather than a text-heavy slide.
