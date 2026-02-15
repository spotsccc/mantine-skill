# TypographyStylesProvider

**Purpose:** Apply Mantine theme styles to raw HTML content.

## Key props

No specific props — wrapper component. Accepts standard `className`, `style`, etc.

## Rules and gotchas

- Use when rendering HTML from external sources (markdown, CMS, rich text).
- Wrap content with `dangerouslySetInnerHTML`.
- Applies theme styles to: `p`, `h1`–`h6`, `ul`, `ol`, `blockquote`, `table`, `a`, `img`, `hr`, `code`, `pre`.
- Does NOT sanitize HTML — sanitize separately before rendering (e.g. DOMPurify).

## Example

```tsx
<TypographyStylesProvider>
  <div dangerouslySetInnerHTML={{ __html: markdownHtml }} />
</TypographyStylesProvider>
```
