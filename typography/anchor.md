# Anchor

**Purpose:** Themed link element.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `href` | string | Link URL |
| `underline` | `"always"` \| `"hover"` \| `"never"` \| `"not-hover"` | Underline behavior |
| `target` | string | `_blank`, `_self`, etc. |
| Inherits | Text props | `size`, `c`, `fw`, `tt`, etc. |

## Rules and gotchas

- Extends Text — all Text props apply.
- Default renders `<a>`.
- Polymorphic — use `component={Link}` with Next.js for client-side routing.
- `underline="hover"` — common pattern (underline on hover only).
- Supports `variant="gradient"` for gradient text links.

## Example

```tsx
<Anchor href="/about">About page</Anchor>

<Anchor href="/articles" underline="hover">Hover to underline</Anchor>

import Link from 'next/link';

<Anchor component={Link} href="/dashboard" underline="hover">Dashboard</Anchor>
```
