# Select

**Purpose:** Single value selection from a list.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `data` | `string[]` or `{value, label}[]` | Options (values must be unique strings) |
| `searchable` | boolean | Enable search/filter |
| `clearable` | boolean | Show clear button |
| `allowDeselect` | boolean | Default true — click same option to clear |
| `nothingFoundMessage` | string | Text when search has no matches (otherwise dropdown hides) |
| `limit` | number | Max visible options in dropdown |
| `maxDropdownHeight` | number | Scroll threshold |
| `value` | `string \| null` | Controlled value |
| `onChange` | `(v: string \| null) => void` | Change handler |
| `withinPortal` | boolean | Render dropdown in portal (default true) |

## Rules and gotchas

- **Values:** `data` values must be unique strings. For `{value, label}[]` — `value` is what gets stored.
- **value/onChange** work with `string | null`, not objects.
- **`nothingFoundMessage`** — set explicitly, e.g. `"Nothing found"`, otherwise empty search hides dropdown.
- **`allowDeselect`** — lets user clear by clicking selected option again.
- **Inside Popover:** pass `comboboxProps={{ withinPortal: false }}`.
- **Groups:** `data: [{ group: 'A', items: [...] }, { group: 'B', items: [...] }]`.

## Example

```tsx
<Select
  label="Country"
  data={['USA', 'France', 'Spain']}
  searchable
  clearable
  nothingFoundMessage="Nothing found"
  value={country}
  onChange={setCountry}
/>
```
