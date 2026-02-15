# NumberInput

**Purpose:** Numeric input with increment/decrement controls.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `min` / `max` | number | Bounds |
| `step` | number | Increment/decrement step |
| `clampBehavior` | `"blur"` \| `"strict"` \| `"none"` | When to clamp value |
| `allowDecimal` | boolean | Allow decimals |
| `allowNegative` | boolean | Allow negative |
| `decimalScale` | number | Max decimal places |
| `fixedDecimalScale` | boolean | Always show fixed decimals |
| `prefix` / `suffix` | ReactNode | Unit or currency symbol |
| `hideControls` | boolean | Hide +/- buttons |
| `handlersRef` | Ref | Ref to `{ increment, decrement }` for programmatic control |

## Rules and gotchas

- **value/onChange:** can be `string | number`. Empty input = `""`.
- Uses `react-number-format` internally.
- **`clampBehavior="strict"`** — prevents typing out-of-range; can be annoying for narrow ranges.
- **`handlersRef`** — access `increment()` / `decrement()` for custom controls.

## Example

```tsx
<NumberInput
  label="Количество"
  min={1}
  max={100}
  step={1}
  value={count}
  onChange={setCount}
  prefix="$"
/>
```
