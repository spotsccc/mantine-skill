# Stack

**Purpose:** Vertical flex container.

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `gap` | MantineSpacing | Vertical spacing between children (default `"md"`) |
| `align` | AlignItems | Horizontal alignment of children |
| `justify` | JustifyContent | Vertical distribution |

## Rules and gotchas

- Vertical only — use `Group` for horizontal, `Flex` for both directions.
- Not polymorphic — always renders a `div`.
- `gap` defaults to `"md"` if omitted.

## Example

```tsx
<Stack gap="md">
  <Box>Item 1</Box>
  <Box>Item 2</Box>
</Stack>

<Stack gap="lg" align="stretch" justify="flex-end">
  <Button>Action</Button>
</Stack>
```
