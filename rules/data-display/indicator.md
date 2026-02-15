---
description: Mantine Indicator — notification dot or count badge on element. Wrap target as child.
---

# Indicator

## Purpose

Notification dot or count badge overlaid on an element (e.g. Avatar, IconButton).

## Key props

| Prop | Type | Notes |
|------|------|-------|
| `label` | ReactNode | Badge content (number, text); omitting shows dot |
| `color` | string | Badge color |
| `size` | number | Badge size |
| `position` | "top-end" \| "top-start" \| "bottom-end" \| "bottom-start" \| "middle-end" \| ... | Placement |
| `offset` | number | Adjust for rounded elements |
| `processing` | boolean | Pulse animation |
| `disabled` | boolean | Hides indicator |
| `inline` | boolean | For fixed-width targets |
| `withBorder` | boolean | Border around badge |

## Rules

- Wrap the target element as a single child.
- Use `inline` when target has fixed width.
- `offset` adjusts position for rounded elements (e.g. circular Avatar).
- `processing` adds pulse animation (e.g. "typing" state).
- `disabled` hides the indicator without unmounting.

## Example

```tsx
<Indicator label={3} size={16} color="red" position="top-end" offset={2}>
  <Avatar src="/user.jpg" alt="User" />
</Indicator>
<Indicator processing position="top-end">
  <ActionIcon><IconBell /></ActionIcon>
</Indicator>
```
