# Slider

**Purpose:** Value selection from a range.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `min` | number | Minimum value (default 0) |
| `max` | number | Maximum value (default 100) |
| `step` | number | Step increment |
| `marks` | `{ value: number; label?: ReactNode }[]` | Visual indicators on the track |
| `label` | `((value: number) => ReactNode)` \| null | Tooltip above thumb; null to hide |
| `labelAlwaysOn` | boolean | Keep label visible always |
| `thumbLabel` | string | `aria-label` for the thumb |
| `color` | MantineColor | Slider color |
| `size` | MantineSize | Track height |
| `inverted` | boolean | Invert filled track direction |
| `disabled` | boolean | Disabled state |

## Rules and gotchas

- **`label`** is a function `(value) => ReactNode` for custom formatting, or `null` to hide the tooltip entirely.
- **`marks`** adds visual tick marks on the track; does not restrict values (use `step` for that).
- **RangeSlider** — use for two-thumb range selection (`value` is `[number, number]`).
- **`thumbLabel`** sets `aria-label` on the thumb for screen readers — always provide for accessibility.

## Example

```tsx
<Slider
  min={0}
  max={100}
  step={10}
  value={value}
  onChange={setValue}
  marks={[
    { value: 0, label: '0%' },
    { value: 50, label: '50%' },
    { value: 100, label: '100%' },
  ]}
  label={(v) => `${v}%`}
  thumbLabel="Volume"
/>

{/* Two-thumb range */}
<RangeSlider min={0} max={1000} value={range} onChange={setRange} />
```
