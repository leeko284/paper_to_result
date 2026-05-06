---
name: paper-insights-pro
description: Deep academic paper analysis and presentation planning for PDF papers, paper titles, local paper paths, or paper collections. Use when the user asks to summarize a paper, create reading notes, prepare a report, design a paper presentation, generate a PPT outline, or produce Marp Markdown. Extract research motivation, contributions, model architecture, algorithms, key figures, formulas, experiments, metrics, conclusions, limitations, and academic insights. Generate notes from a provided template, references/PaperNote_template.md, or a discovered PaperNote_template.md. When PPT templates, historical .pptx files, uploaded decks, or a PPT_template directory are available, first extract slide style and layout rules, then adapt the paper presentation outline or Marp Markdown to match that style. Preserve important English terms, avoid fabricating missing data, and clearly flag uncertain or unavailable information.
---

# Paper Insights Pro

Use this skill to turn academic papers into structured research notes and presentation-ready outlines. Prefer evidence from the paper text, tables, formulas, captions, and figures over generic background knowledge.

## Inputs

Accept any combination of:

- PDF paper files, paper titles, local paths, DOI/arXiv links, or paper collections.
- User note templates, especially `PaperNote_template.md`.
- PPT templates, historical `.pptx` files, uploaded slide decks, or `PPT_template/` folders.
- User requirements for page count, language, Marp output, target audience, or report style.

If multiple templates are available, apply this priority:

1. User explicitly named template or uploaded file.
2. Local `PPT_template/` under the working directory.
3. `assets/PPT_template/` inside this skill.
4. Generic academic presentation style.

## Workflow

1. Identify source papers and available templates.
2. Extract paper text, captions, tables, formulas, and figure references. Use OCR or fallback extraction only when needed.
3. Build a paper evidence map: problem, motivation, contribution, method, model architecture, algorithm flow, experiments, metrics, results, limitations.
4. Generate notes with the user's template. If no template is provided, use `references/PaperNote_template.md`; if that file is unavailable, use the note sections in this skill.
5. If PPT templates or historical decks exist, analyze slide style before designing the presentation. Use `references/ppt_style_checklist.md` when style extraction is needed.
6. Produce either a text PPT outline or Marp Markdown, depending on the user's requested output.
7. Clearly mark missing, uncertain, or non-extractable information.

## Paper Notes

Default note structure:

- Title, venue, year, authors, DOI/link if available.
- Research core: problem, method, result, significance.
- Contributions: list the paper's explicit claimed contributions and explain their value.
- Method: describe pipeline, model modules, algorithm steps, losses, formulas, and training/inference logic.
- Figures and tables: record figure/table number, caption, location, and what the figure/table proves.
- Experiments: datasets, metrics, baselines, implementation details, main results, ablation, robustness, error analysis.
- Limitations: state what the authors admit and what is implied by the evidence.
- Personal insights: reusable ideas, open questions, possible follow-up work.

Use Markdown headings that match the selected template. Name generated note files as:

```text
note_[original-file-name].md
```

## PPT Style Extraction

When templates or historical decks are provided, summarize style before drafting slides:

- Page size and aspect ratio.
- Common slide types: cover, overview, method, experiment, conclusion.
- Title placement, hierarchy, and text density.
- Font family, font size range, bold/italic habits, bilingual text pattern.
- Dominant colors, accent colors, background usage.
- Layout patterns for architecture diagrams, formulas, tables, and comparison results.
- Typical visual rhythm: dense academic pages, clean conference style, defense style, or project-report style.
- Reusable constraints: margins, footer/header, page number, logos, section dividers.

Do not copy irrelevant content from historical decks. Extract style rules and adapt the paper content to them.

## PPT Outline

Default 5-slide structure:

```text
Slide 1: Title and summary
Slide 2: Research problem, motivation, and overall method
Slide 3: Model architecture and core algorithm
Slide 4: Experimental results and comparison analysis
Slide 5: Conclusion, limitations, and insights
```

For each slide provide:

- Slide title.
- Main message.
- Recommended layout.
- Bullet content.
- Figure/table/formula placement.
- Speaker explanation points.
- Template/style mapping if a PPT template was analyzed.

For Slide 2-3, describe key figures in detail, for example:

```text
Place Figure 2 here: overall network architecture. It should show input features, encoder, fusion module, prediction head, and the direction of information flow.
```

For Slide 4, reproduce core metrics as Markdown tables when the paper provides numeric results. Never invent values. Use `not reported` or `paper does not specify` for missing values.

## Marp Output

When the user asks for Marp, output valid Marp Markdown:

```markdown
---
marp: true
theme: default
paginate: true
---

# Paper Title

---

## Slide Title
```

If a PPT style was extracted, express the style through Marp-safe choices such as heading hierarchy, concise page notes, table formatting, and comments describing where template visuals should be applied.

## Reliability Rules

- Keep academic tone.
- Preserve important English technical terms; add Chinese explanations when useful.
- Distinguish paper facts from interpretation.
- Do not fabricate missing experiments, metrics, datasets, formulas, or conclusions.
- If figure images cannot be extracted, summarize from captions and surrounding text, then mark the figure location.
- If PDF extraction is incomplete, state the extraction limitation and base conclusions only on available evidence.
