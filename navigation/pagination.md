# Pagination

**Purpose:** Page number navigation (lists, tables).

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `total` | number | Total pages (required) |
| `value` | number | Current page |
| `onChange` | (page) => void | Page change handler |
| `siblings` | number | Neighbors count (default 1) |
| `boundaries` | number | Edge pages shown (default 1) |
| `withPages` | boolean | Show page numbers |
| `withControls` | boolean | Show prev/next buttons |
| `getItemProps` | (page) => props | Custom props per page (e.g. `href` for links) |

## Rules and gotchas

- Controlled via `value` + `onChange`
- `getItemProps` useful for making pages into links (SEO, deep linking)
- Compound components available for fully custom layout
- `total` is required — calculate from `Math.ceil(itemsCount / perPage)`

## Example

```tsx
const [page, setPage] = useState(1);
const totalPages = Math.ceil(totalItems / perPage);

<Pagination
  total={totalPages}
  value={page}
  onChange={setPage}
  siblings={1}
/>
```
