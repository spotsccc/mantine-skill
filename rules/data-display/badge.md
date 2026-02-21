# Badge

**Purpose:** Status label, tag, or count. Polymorphic, supports icons.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `variant` | "filled" \| "light" \| "outline" \| "dot" \| "transparent" \| "gradient" \| "default" \| "white" | Controls appearance |
| `color` | string | Theme color or CSS color |
| `size` | "xs"\..."xl" | Size |
| `radius` | "xs"\..."xl" \| number | Corner radius |
| `circle` | boolean | Circular (min-width = height) |
| `fullWidth` | boolean | 100% width |
| `leftSection` \| `rightSection` | ReactNode | Icons |
| `gradient` | object | For variant="gradient" |
| `autoContrast` | boolean | Adjust text contrast; only for filled |

## Rules and gotchas

- Polymorphic: `component` prop to change root element.
- `circle` makes it circular (min-width equals height).
- `autoContrast` works only with `variant="filled"`.
- `color` supports CSS colors and theme colors.

## Example

```tsx
<Group>
  <Badge variant="filled" color="blue">New</Badge>
  <Badge variant="light" color="green">Active</Badge>
  <Badge variant="outline" color="red">Rejected</Badge>
  <Badge variant="dot" color="yellow">Pending</Badge>
  <Badge circle size="lg">5</Badge>
</Group>
```
