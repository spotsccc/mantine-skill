# Radio

**Purpose:** Single selection from a group (radio button).

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `label` | ReactNode | Label text |
| `description` | ReactNode | Helper text |
| `error` | ReactNode | Validation message |
| `color` | MantineColor | Checked color |
| `size` | MantineSize | Radio size |
| `labelPosition` | `"left"` \| `"right"` | Label side |
| `icon` | ReactNode | Custom checked icon |
| `iconColor` | MantineColor | Icon color |

## Rules and gotchas

- **Radio.Group** is required for single-selection behavior — provides shared `value` and `onChange`.
- **Radio.Card** — card-style radio for richer selection UI (e.g. plan picker).
- **Tooltip:** use `refProp="rootRef"` on Tooltip when wrapping Radio.
- `theme.cursorType: 'pointer'` for pointer cursor on label.

## Example

```tsx
<Radio.Group
  value={selected}
  onChange={setSelected}
  label="Select option"
  description="Pick one"
>
  <Radio value="a" label="Option A" />
  <Radio value="b" label="Option B" />
  <Radio value="c" label="Option C" />
</Radio.Group>
```
