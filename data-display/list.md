---
description: Mantine List — styled ordered or unordered list. Icon sets default marker.
---

# List

## Purpose

Styled ordered or unordered list with custom markers.

## Key props

| Prop | Type | Notes |
|------|------|-------|
| `type` | "ordered" \| "unordered" | ol vs ul |
| `icon` | ReactNode | Global marker for all items |
| `spacing` | "xs"\..."xl" | Gap between items |
| `center` | boolean | Align icon with text vertically |
| `size` | "xs"\..."xl" | Text and icon size |
| `withPadding` | boolean | Padding for nested lists |
| `listStyleType` | string | CSS list-style-type override |

## Rules

- `icon` on List sets default marker for all List.Item.
- List.Item can override with its own `icon` prop.
- `withPadding` adds indent for nested lists.
- `center` aligns icon with text vertically (useful with custom icons).

## Example

```tsx
<List type="unordered" icon={<IconCircleFilled size={8} />} spacing="sm" center>
  <List.Item>First step</List.Item>
  <List.Item icon={<IconCheck size={12} />}>Completed</List.Item>
  <List.Item>Third step</List.Item>
</List>
```
