# Box

**Purpose:** Generic wrapper — renders `div` with no default styles.

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `component` | React element type | Polymorphic — can be any HTML element or component |
| All style props | — | `m`, `p`, `c`, `bg`, `w`, `h`, `ta`, `ff`, `fs`, etc. |

## Rules and gotchas

- Base for all Mantine components — use when you need a plain element with style props.
- Polymorphic via `component` — e.g. `component="section"` or `component={Link}`.
- Prefer semantic components (`Stack`, `Group`, `Paper`) when applicable.

## Example

```tsx
<Box p="md" bg="gray.1">
  Content
</Box>

<Box component="section" m="xl" w={200} h={100}>
  Custom element
</Box>
```
