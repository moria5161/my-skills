---
name: rengroup-ppt-skill
description: Create, edit, restyle, and review Ren Group (任组/课题组) academic PowerPoint presentations using the bundled group template and house style. Use for .pptx slide decks, thesis defenses, group meetings, research reports, method/result presentations, or any request that asks for an 任组 PPT or requires the Ren Group template, typography, charts, tables, conclusion boxes, and visual QA rules.
---

# Ren Group PPT

Create research presentations that look like they were prepared inside the group, not from a generic slide generator.

## Required resources

- Start from `assets/任组PPT模板.pptx`. Preserve its slide size, master, page-number treatment, and reusable layouts.
- If the user supplies a newer 任组 template, that file overrides the bundled asset. Its title and conclusion-frame colors take precedence over all numeric fallback values in this skill.
- Read `references/style-guide.md` completely before creating or editing slides.
- Read `references/template-map.md` when choosing or duplicating template slides.
- Use the general PPTX editing workflow and tools available in the environment for unpacking, editing, rendering, and validation.

## Workflow

1. Inspect the source material and identify the presentation purpose, audience, and main scientific claim.
2. Build a concise storyline. Prefer `problem → method → evidence → interpretation → conclusion` for research reports.
3. Analyze the bundled template with thumbnails and text extraction before selecting layouts.
4. Map content to varied template layouts. Duplicate template slides rather than rebuilding the visual system from scratch.
5. Replace every placeholder, sample image, citation, `xxx`, and example conclusion. Remove unused placeholder shapes completely.
6. Apply the house style below and the full rules in `references/style-guide.md`.
7. Run `python scripts/audit_ppt.py output.pptx`. When a newer template is supplied, add `--template path/to/new-template.pptx`.
8. Extract text to check content and render every slide to images for visual QA. Fix issues and repeat the audit after at least one revision cycle.

## Non-negotiable house style

- Use 黑体 for Chinese and Arial for English, including charts, legends, tables, labels, citations, and annotations. Split mixed-language runs when necessary.
- Center every content-slide title at the top. Inherit the template title color (`#800000`). Never place the title at the upper left.
- Use 20–24 pt for the main narrative and conclusion statements.
- Use 14–16 pt for legends, annotations, citations, table text, and text inside figures. Keep chart-axis text at least 12 pt.
- Put a slide-level conclusion on result and discussion slides in a lower-right or bottom conclusion box. Duplicate the template conclusion shape so its no-fill treatment and `#C00000` outline are preserved; use black 20–24 pt text.
- Keep tables unfilled and visually light. Use only necessary thin rules; do not apply colored header fills.
- Prefer SVG/vector artwork. Use high-resolution raster images without stretching; keep chart labels readable at presentation scale.
- Keep content-slide backgrounds clean and consistent with the template. Do not add decorative gradients, dark panels, sand backgrounds, or unrelated motifs.
- Do not add a research date or project date in the lower-left corner of content slides. A cover date is allowed only when requested or required by the template.
- Preserve whitespace. Do not shrink essential text below the specified size to make overcrowded content fit; split the slide instead.

## Scientific communication rules

- Lead each slide with one scientific message, not a list of everything that was done.
- Show evidence next to its interpretation. Keep captions close to their figure or table.
- State uncertainty, sample size, validation design, and limitations where they affect the conclusion.
- Use concise academic language. Avoid promotional wording and unsupported claims.
- On comparison slides, make the baseline, proposed method, metric, and direction of improvement explicit.

## QA requirements

- Treat `scripts/audit_ppt.py` warnings as items to inspect, not as permission to ignore them.
- Check for title placement/color, font families and sizes, conclusion-frame styling, unfilled tables, image resolution, chart-axis readability, and unwanted bottom-left date text.
- Inspect every rendered slide for overlap, clipping, inconsistent alignment, cramped blocks, stretched figures, low contrast, and leftover template content.
- Do not deliver until the deck passes structural validation and a full visual pass reveals no new issues.
