# Typography Components

## Decision tree

- **Regular text** → [Text](text.md) (`size`, `c`, `fw`, `truncate`, `lineClamp`)
- **Headings h1–h6** → [Title](title.md) (`order`, `size`, `textWrap`)
- **Links** → [Anchor](anchor.md) (`underline`, `component={Link}` for Next.js)
- **Inline/block code** → [Code](code.md) (`block` for multiline)
- **Highlight search matches** → [Highlight](highlight.md) (`highlight`, `highlightStyles`)
- **Render raw HTML with theme styles** → [TypographyStylesProvider](typography-styles-provider.md)

## Common patterns

- **Text** `c="dimmed"` — secondary/muted text
- **Title** `order` controls semantic heading level; `size` can override visual size independently
- **Anchor** `component={Link}` — use with Next.js routing for client-side navigation
- **TypographyStylesProvider** — wrap `dangerouslySetInnerHTML` content (markdown, CMS HTML)

## Components

| Component | File | Purpose |
|-----------|------|---------|
| Text | [text.md](text.md) | Display text with theme styles |
| Title | [title.md](title.md) | Semantic headings h1–h6 |
| Anchor | [anchor.md](anchor.md) | Themed link element |
| Code | [code.md](code.md) | Inline and block code |
| Highlight | [highlight.md](highlight.md) | Highlight matching substrings |
| TypographyStylesProvider | [typography-styles-provider.md](typography-styles-provider.md) | Apply theme to raw HTML |
