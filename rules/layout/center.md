# Center

**Purpose:** Center content vertically and horizontally.

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `inline` | boolean | Use `display: inline-flex` instead of `flex` |

## Rules and gotchas

- Uses flexbox centering (`display: flex`, `align-items: center`, `justify-content: center`).
- Use `inline` when placing inside text flow.
- For simple text centering, prefer `ta="center"` style prop on parent.

## Example

```tsx
<Center h={200}>
  <Loader />
</Center>

<Center inline>
  <IconCheck size={16} />
</Center>
```
