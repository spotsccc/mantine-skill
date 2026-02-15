# Container

**Purpose:** Max-width centered content wrapper.

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `size` | `"xs" \| "sm" \| "md" \| "lg" \| "xl"` or number | Max-width preset or px value |
| `fluid` | boolean | 100% width, no max-width |
| `strategy` | `"block"` \| `"grid"` | Strategy for layout (v8.2+). `"grid"` enables `data-breakout` for full-width children |

## Rules and gotchas

- **`size` is NOT responsive** — same value at all viewports. Use CSS Modules `classNames` for responsive max-width if needed.
- Use `fluid` instead of `size="100%"` — the latter is not a valid prop value.
- `strategy="grid"` enables `data-breakout` attribute on children for full-bleed content inside container.

## Example

```tsx
<Container size="lg">
  <p>Centered content with max-width</p>
</Container>

<Container fluid>Full-width content</Container>
```
