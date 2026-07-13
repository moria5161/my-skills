# 任组 PPT style guide

## Visual identity

| Element | Rule |
|---|---|
| Template | Always use `assets/任组PPT模板.pptx` as the starting presentation |
| Slide size | Preserve template size: 13.333 × 7.5 in (16:9) |
| Title color | Template maroon `#800000` |
| Conclusion outline | Template red `#C00000` |
| Body color | Black `#000000` |
| Background | Use the clean template background; do not invent decorative backgrounds |
| Chinese font | 黑体 |
| English font | Arial |

The template is the source of truth for title color and conclusion-frame color. In the bundled version, preserve `#800000` for titles and duplicate the template conclusion frame so its `#C00000` outline treatment remains intact. If the user provides a newer template, inspect and inherit its colors instead of forcing these fallback values.

## Typography

| Role | Size | Alignment and treatment |
|---|---:|---|
| Content-slide title | Inherit the template size unless adjustment is necessary | Top center, bold, template color `#800000` |
| Main narrative | 20–24 pt | Prefer left alignment; use short statements |
| Slide conclusion | 20–24 pt | Black text inside the conclusion frame |
| Legend and annotation | 14–16 pt | Keep close to the related graphic |
| Table content | 14–16 pt | Align by data type; avoid cramped cells |
| Text inside figures | 14–16 pt | Regenerate the figure if embedded text is smaller |
| Axis labels and ticks | At least 12 pt | Prefer 12–14 pt; never rely on post-scaling |
| Citations and edge notes | 14–16 pt | Concise and visually secondary |

Set Chinese and English fonts explicitly. For mixed text such as `峰强比 Ratio`, use separate runs so Chinese is 黑体 and English is Arial.

## Slide title

- Place each content-slide title in a full-width title box at the top center.
- Use the title color inherited from the template (`#800000`).
- Do not place section labels or titles in the upper-left corner.
- Preserve the template separator if it is part of the master; do not add a second decorative title line.
- Keep the title on one line when possible. Shorten it before shrinking it excessively.

## Conclusion frame

Use the frame on result, comparison, discussion, and summary slides when a page-level conclusion exists.

- Position: bottom spanning the main content width, or lower-right when the layout requires it.
- Border: duplicate the template frame and retain its `#C00000` outline color and line treatment.
- Fill: none/transparent.
- Text: black, 20–24 pt, concise, normally one or two lines.
- Do not use a filled red callout, shadow, or glow. Preserve the template's rounded, dashed outline when duplicating its conclusion frame.
- The conclusion must interpret the evidence on that slide; it must not merely repeat the title.

## Figures and charts

- Prefer SVG, EMF, PDF-derived vector art, or editable native charts.
- For raster figures, target at least 150 ppi at the displayed size; use 200–300 ppi for detailed spectra and microscopy images.
- Never stretch an image non-proportionally.
- Crop unused white margins before placement.
- Use Arial for English chart text and 黑体 for Chinese chart text.
- Use 14–16 pt for legends, annotations, and labels within the plotting area.
- Keep axis labels and ticks at least 12 pt after insertion into the slide.
- Use consistent line widths and colors across related plots.
- Explain statistical bars, bands, symbols, and sample sizes when they affect interpretation.

## Tables

- Use no cell fill, including the header row, unless the user explicitly requests emphasis.
- Use thin black or neutral-gray rules only where needed for reading structure.
- Keep 14–16 pt text and adequate cell padding.
- Align numeric columns consistently and use the same number of decimal places within a metric.
- Reduce columns, shorten headers, or split the table instead of shrinking text.
- Use bold text, a slightly heavier rule, or spacing—not colored fills—to distinguish headers.

## Layout and density

- Use one main message per slide.
- Keep at least 0.5 in outer margins and 0.3 in between independent blocks where the template allows.
- Favor a dominant visual with supporting interpretation over many equally weighted boxes.
- Use the three-panel layout for direct comparisons and the single-figure layout for a main result plus interpretation.
- Avoid text-only result slides when a figure, spectrum, workflow, or compact table can carry the evidence.
- Do not add a date, project timestamp, or study period in the lower-left corner of content slides.

## Content checklist

- Does the title state the topic clearly?
- Is the result visible without reading the conclusion first?
- Does the conclusion explain why the result matters?
- Are sample size, uncertainty, and validation assumptions shown where relevant?
- Are all placeholders and example citations removed?
- Are abbreviations defined on first use?
