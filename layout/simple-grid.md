# SimpleGrid

**Purpose:** Equal-width responsive grid (CSS Grid).

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `cols` | number or responsive object | Column count per breakpoint |
| `spacing` | MantineSpacing or responsive | Horizontal and vertical gap |
| `verticalSpacing` | MantineSpacing or responsive | Override vertical gap |
| `type` | `"media"` \| `"container"` | `"container"` needs exact px/em values (not theme breakpoint names) |

## Rules and gotchas

- All children get equal width — use `Grid` if you need different column widths per child.
- `cols` and `spacing` support responsive objects: `{{ base: 1, sm: 2, lg: 4 }}`.
- `type="container"` requires exact px/em values for breakpoints, not theme names like `"sm"` or `"md"`.

## Example

```tsx
<SimpleGrid cols={{ base: 1, sm: 2, lg: 4 }} spacing="md">
  <Card>Item 1</Card>
  <Card>Item 2</Card>
  <Card>Item 3</Card>
  <Card>Item 4</Card>
</SimpleGrid>
```
