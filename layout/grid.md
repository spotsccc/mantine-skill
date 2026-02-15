# Grid

**Purpose:** Responsive 12-column grid system.

## Key props

**Grid:**
| Prop | Type | Description |
|------|------|--------------|
| `columns` | number | Column count (default 12) |
| `gutter` | MantineSpacing or responsive object | Spacing between cols |
| `grow` | boolean | Children stretch to fill |
| `justify` | JustifyContent | Horizontal alignment |
| `align` | AlignItems | Vertical alignment |
| `overflow` | `"visible"` \| `"hidden"` | Use `"hidden"` when Grid has no parent padding |
| `type` | `"media"` \| `"container"` | `"container"` enables container queries (requires `breakpoints` prop) |

**Grid.Col:**
| Prop | Type | Description |
|------|------|--------------|
| `span` | 1–12, `"auto"`, `"content"` or `{ base, xs, sm, md, lg, xl }` | Column span |
| `offset` | number or responsive object | Offset columns |
| `order` | number or responsive object | Flex order |

## Rules and gotchas

- `span` supports responsive objects: `{{ base: 12, md: 6, lg: 3 }}`.
- When `span + offset` exceeds `columns`, the col wraps to next row.
- Use `overflow="hidden"` when Grid has no parent with padding to prevent horizontal scroll.
- `type="container"` enables container queries — must set `breakpoints` prop too.

## Example

```tsx
<Grid>
  <Grid.Col span={{ base: 12, sm: 6, lg: 4 }}>Col 1</Grid.Col>
  <Grid.Col span={{ base: 12, sm: 6, lg: 4 }}>Col 2</Grid.Col>
  <Grid.Col span={{ base: 12, sm: 6, lg: 4 }}>Col 3</Grid.Col>
</Grid>
```
