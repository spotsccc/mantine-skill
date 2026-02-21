# TagsInput

**Purpose:** Free-form tag entry with optional suggestions.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `data` | `string[]` | Suggestions (optional) |
| `maxTags` | number | Max tags allowed |
| `splitChars` | `string[]` | Default `[","]` — chars that create new tag on paste/type |
| `allowDuplicates` | boolean | Default false — case-insensitive duplicate check |
| `acceptValueOnBlur` | boolean | Default true — blur creates tag from current input |
| `value` | `string[]` | Controlled value |
| `onChange` | `(v: string[]) => void` | Change handler |

## Rules and gotchas

- **Arbitrary values** — unlike MultiSelect, user can add any string (not limited to `data`).
- **`data`** — suggestions only; user can type values not in list.
- Duplicates are case-insensitive by default (`allowDuplicates={false}`).
- **`splitChars`** — also work on paste (e.g. comma-separated list).
- **Inside Popover:** use `withinPortal={false}` via `comboboxProps`.

## Example

```tsx
<TagsInput
  label="Tags"
  data={['travel', 'vacation', 'beach']}
  splitChars={[',', ' ', ';']}
  maxTags={10}
  value={tags}
  onChange={setTags}
/>
```
