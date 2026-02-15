# MultiSelect

**Purpose:** Multiple values selection from a list.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `data` | `string[]` or `{value, label}[]` | Options |
| `searchable` | boolean | Enable search |
| `clearable` | boolean | Clear all button |
| `hidePickedOptions` | boolean | Remove selected from dropdown |
| `maxValues` | number | Max allowed selections |
| `value` | `string[]` | Controlled value |
| `onChange` | `(v: string[]) => void` | Change handler |
| `nothingFoundMessage` | string | Empty search text |

## Rules and gotchas

- **Only values from `data`** — unlike TagsInput, user cannot add arbitrary values.
- **`value`** is `string[]`, not objects.
- **`hidePickedOptions`** — selected options disappear from dropdown (common UX).
- Disabled options can still be set programmatically via `value`.

## Example

```tsx
<MultiSelect
  label="Категории"
  data={categories}
  searchable
  hidePickedOptions
  maxValues={5}
  value={selected}
  onChange={setSelected}
  nothingFoundMessage="Ничего не найдено"
/>
```
