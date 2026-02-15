# Progress

**Purpose:** Progress bar indicator. Single or multi-section (stacked segments).

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `value` | number | 0–100, completion percentage |
| `color` | MantineColor | Theme color key |
| `size` | MantineSize | Bar thickness |
| `radius` | MantineRadius | Corner radius |
| `striped` | boolean | Striped pattern |
| `animated` | boolean | Animated stripes (implies striped) |
| `transitionDuration` | number | Animation duration ms |
| `orientation` | string | `"horizontal"` \| `"vertical"` |

## Compound components

- **Progress.Root** — container for multi-section progress
- **Progress.Section** — each segment (own `value` and `color`)
- **Tooltip** — wrap Progress.Section for value on hover

## Rules and gotchas

- **Multi-section:** Use `Progress.Root` with multiple `Progress.Section` children (each has own `value`, `color`).
- **Tooltip:** Add Tooltip to Progress.Section for hover value display.
- `animated` implies `striped` — no need to set both.

## Example

```tsx
<Progress value={75} color="blue" size="md" radius="xl" />

<Progress.Root size="xl">
  <Progress.Section value={40} color="blue" />
  <Progress.Section value={30} color="green" />
  <Progress.Section value={15} color="yellow" />
</Progress.Root>
```
