# Title

**Purpose:** Semantic headings h1–h6.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `order` | `1`–`6` | Semantic level; sets HTML element (h1–h6) and default size |
| `size` | `"h1"`–`"h6"` \| MantineSize \| number | Override visual size only; does NOT change HTML element |
| `lineClamp` | number | Max visible lines |
| `textWrap` | `"wrap"` \| `"balance"` \| `"pretty"` | Wrapping behavior |

## Rules and gotchas

- `order` — sets both HTML element and default visual size.
- `size` — overrides visual size only. Example: `order={3}` with `size="h1"` renders semantic h3 but visually like h1.
- No margins by default — add `mt`, `mb`, etc. if needed.
- `textWrap="balance"` — improves heading wrapping for multi-line titles.
- NOT polymorphic — always renders h1–h6.

## Example

```tsx
<Title order={1}>Page Title</Title>

<Title order={3} size="h1">Visually large, semantically h3</Title>

<Title order={2} textWrap="balance">Long heading that wraps nicely</Title>

<Title order={4} lineClamp={2}>Heading truncated to 2 lines</Title>
```
