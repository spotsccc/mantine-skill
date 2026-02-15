# Textarea

**Purpose:** Multi-line text input.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `autosize` | boolean | Auto-adjust height as user types |
| `minRows` | number | Min rows when `autosize` |
| `maxRows` | number | Max rows when `autosize` (no limit if omitted) |
| `resize` | `"vertical"` \| `"both"` \| `"none"` | Resize handle |
| + TextInput props | — | `label`, `description`, `error`, `size`, etc. |

## Rules and gotchas

- **`autosize`** — uses `react-textarea-autosize` internally. Set `minRows` / `maxRows` to control bounds.
- Without `maxRows` autosize grows infinitely — use for long content with caution.
- `resize="none"` removes drag handle if you want only autosize behavior.

## Example

```tsx
<Textarea
  label="Описание"
  placeholder="Введите текст..."
  autosize
  minRows={3}
  maxRows={10}
  error={errors.description?.message}
/>
```
