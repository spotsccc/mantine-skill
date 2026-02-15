# Burger

**Purpose:** Mobile navigation toggle button (hamburger ↔ close icon).

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `opened` | boolean | Open state (lines → X) |
| `onClick` | () => void | Toggle handler |
| `color` | MantineColor | Line color |
| `size` | MantineSize | Button size |
| `lineSize` | number | Line width |
| `transitionDuration` | number | Animation ms |

## Rules and gotchas

- **MUST** set `aria-label` for accessibility (e.g. "Open menu" / "Close menu")
- Use `useDisclosure` hook for state: `const [opened, { toggle }] = useDisclosure()`
- Pair with AppShell `navbar={{ collapsed: { mobile: !opened } }}`

## Example

```tsx
const [opened, { toggle }] = useDisclosure();

<Burger
  opened={opened}
  onClick={toggle}
  aria-label={opened ? 'Close menu' : 'Open menu'}
  size="sm"
/>
```
