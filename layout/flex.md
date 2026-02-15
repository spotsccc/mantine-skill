# Flex

**Purpose:** Full-control flex container (alternative to Stack/Group).

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `gap` | MantineSpacing or responsive | Spacing between children |
| `direction` | FlexDirection or responsive | `row`, `column`, etc. |
| `wrap` | FlexWrap or responsive | Wrap behavior |
| `justify` | JustifyContent | Main axis alignment |
| `align` | AlignItems | Cross axis alignment |
| `columnGap` | MantineSpacing | Separate horizontal gap |
| `rowGap` | MantineSpacing | Separate vertical gap |

## Rules and gotchas

- Polymorphic — use `component` to render as different element.
- All props support responsive objects: `{{ base: 'column', sm: 'row' }}`.
- More verbose than Stack/Group — prefer Stack/Group when direction is fixed.

## Example

```tsx
<Flex direction={{ base: 'column', sm: 'row' }} gap="md">
  <Box>Item 1</Box>
  <Box>Item 2</Box>
</Flex>

<Flex wrap="wrap" gap="xs" justify="flex-end">
  <Badge>Tag</Badge>
  <Badge>Tag</Badge>
</Flex>
```
