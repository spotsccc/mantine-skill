# Space

**Purpose:** Add horizontal or vertical spacing between elements.

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `w` | MantineSpacing | Horizontal space (width) |
| `h` | MantineSpacing | Vertical space (height) |

## Rules and gotchas

- Prefer `gap` in Stack/Group/Flex over Space — gap is the standard layout approach.
- Use Space only when `gap` is not available (e.g., between unrelated siblings, legacy layouts).

## Example

```tsx
<Box>
  <Text>First block</Text>
  <Space h="md" />
  <Text>Second block</Text>
</Box>

<Group>
  <Badge>One</Badge>
  <Space w="sm" />
  <Badge>Two</Badge>
</Group>
```
