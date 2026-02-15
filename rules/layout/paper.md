# Paper

**Purpose:** Surface with background and optional shadow/border.

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `shadow` | `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` | Box shadow |
| `radius` | MantineRadius | Border radius |
| `withBorder` | boolean | Add border |
| `component` | React element type | Polymorphic |

## Rules and gotchas

- Background auto-adjusts to color scheme (white in light, dark in dark mode).
- Polymorphic — can render as `article`, `section`, etc.
- Use for cards, dropdowns, modal backgrounds.

## Example

```tsx
<Paper shadow="sm" radius="md" withBorder p="xl">
  Card-like content
</Paper>

<Paper component="article" shadow="xs" radius="sm">
  Article surface
</Paper>
```
