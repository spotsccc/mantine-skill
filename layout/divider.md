# Divider

**Purpose:** Horizontal or vertical line separator.

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `orientation` | `"horizontal"` \| `"vertical"` | Default horizontal |
| `label` | ReactNode | Text in the middle of the line |
| `labelPosition` | `"left"` \| `"center"` \| `"right"` | Label alignment |
| `size` | MantineSpacing or number | Line thickness |
| `color` | MantineColor | Line color |
| `variant` | `"solid"` \| `"dashed"` \| `"dotted"` | Line style |

## Rules and gotchas

- Horizontal by default — use `orientation="vertical"` for vertical dividers.
- Vertical dividers need explicit height — set `h` style prop.
- Use `label` for section dividers with text (e.g. "Or" between form sections).

## Example

```tsx
<Divider my="md" />

<Divider my="md" label="Or" labelPosition="center" />

<Group>
  <Text>Left</Text>
  <Divider orientation="vertical" h={24} />
  <Text>Right</Text>
</Group>
```
