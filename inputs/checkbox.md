# Checkbox

**Purpose:** Boolean toggle (checkmark style).

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `label` | ReactNode | Label text |
| `description` | ReactNode | Helper text |
| `error` | ReactNode | Validation message |
| `color` | MantineColor | Checked color |
| `size` | MantineSize | Checkbox size |
| `radius` | MantineRadius | Corner radius |
| `indeterminate` | boolean | Indeterminate state (overrides checked visual) |
| `labelPosition` | `"left"` \| `"right"` | Label side |
| `icon` | ReactNode | Custom checked icon |
| `iconColor` | MantineColor | Icon color |

## Rules and gotchas

- **`indeterminate`** overrides `checked` visually (e.g. "select all").
- **Tooltip:** use `refProp="rootRef"` on Tooltip when wrapping Checkbox.
- **Checkbox.Group** — multiple checkboxes with shared `value` and `onChange`.
- **Checkbox.Card** — card-style checkbox for settings.
- `theme.cursorType: 'pointer'` for pointer cursor on label.

## Example

```tsx
<Checkbox
  label="Согласен с условиями"
  error={errors.agree?.message}
  checked={checked}
  onChange={(e) => setChecked(e.currentTarget.checked)}
/>

<Checkbox.Group value={selected} onChange={setSelected}>
  <Checkbox value="a" label="Вариант A" />
  <Checkbox value="b" label="Вариант B" />
</Checkbox.Group>
```
