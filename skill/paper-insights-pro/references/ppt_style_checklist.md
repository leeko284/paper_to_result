# PPT Style Extraction Checklist

Use this checklist when the user provides PPT templates, historical slide decks, or a `PPT_template/` directory.

## Template Priority

1. User explicitly selected template.
2. Uploaded PPT files.
3. Working-directory `PPT_template/`.
4. Skill `assets/PPT_template/`.

When multiple decks are provided, extract shared patterns. If decks conflict, follow the user's selected deck or the most relevant academic/reporting deck.

## Analyze

- Aspect ratio and slide dimensions.
- Slide type inventory: cover, agenda, section divider, method, architecture, experiment, comparison table, conclusion.
- Layout grid: margins, title position, body columns, figure area, caption style.
- Typography: font family, title size, body size, bold emphasis, bilingual usage.
- Color system: background, dominant colors, accent colors, table colors, line colors.
- Visual language: icons, diagrams, image masks, arrows, callouts, borders, page numbers.
- Academic density: amount of text per slide, table density, formula placement, caption length.
- Reusable slide mapping: which template page type fits each paper presentation slide.

## Output

Summarize style as concrete reusable rules, then apply those rules to the generated outline:

```markdown
### Extracted PPT Style

- Aspect ratio:
- Main colors:
- Title pattern:
- Body layout:
- Figure/table placement:
- Best matching slide types:

### Application to This Paper

| Generated slide | Template style/page type | Adaptation notes |
|---|---|---|
| Slide 1 | Cover |  |
```
