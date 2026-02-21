# Switch

**Purpose:** Boolean toggle (switch style) for on/off settings.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `label` | ReactNode | Label text |
| `description` | ReactNode | Helper text |
| `error` | ReactNode | Validation message |
| `color` | MantineColor | Active color |
| `size` | MantineSize | Switch size |
| `onLabel` / `offLabel` | ReactNode | Labels when on/off |
| `thumbIcon` | ReactNode | Icon inside thumb |
| `labelPosition` | `"left"` \| `"right"` | Label side |

## Rules and gotchas

- **Prefer Switch over Checkbox** for on/off settings with instant effect (e.g. dark mode, notifications).
- **Tooltip:** use `refProp="rootRef"` when wrapping Switch in Tooltip.
- **Switch.Group** — multiple switches with shared state.
- `theme.cursorType: 'pointer'` for pointer cursor on label.

## Example

```tsx
<Switch
  label="Notifications"
  description="Receive email about new articles"
  checked={enabled}
  onChange={(e) => setEnabled(e.currentTarget.checked)}
/>

<Switch onLabel="On" offLabel="Off" thumbIcon={<IconCheck size={12} />} />
```
