# Highlight

**Purpose:** Highlight matching substrings in text.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `children` | string | Text to search in (required) |
| `highlight` | string \| string[] | Substring(s) to highlight; array for multiple terms |
| `highlightStyles` | React.CSSProperties \| Record | Styles for highlighted spans |
| `color` | MantineColor | Highlight background color |
| Inherits | Text props | `size`, `c`, etc. |

## Rules and gotchas

- Extends Text.
- `highlight` — can be array for multiple search terms.
- Case-insensitive matching.
- If no match — text renders normally without highlight wrapper.
- Use for search results, autocomplete suggestions, keyword emphasis.

## Example

```tsx
<Highlight highlight="mantine">Mantine is a React component library</Highlight>

<Highlight highlight={['Paris', 'Eiffel']} highlightStyles={{ fontWeight: 700 }}>
  Paris and the Eiffel Tower are must-see
</Highlight>
```
