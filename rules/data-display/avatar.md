---
description: Mantine Avatar — user photo, initials, or placeholder. Avatar.Group for stacking.
---

# Avatar

## Purpose

User photo, initials, or placeholder. Avatar.Group stacks multiple avatars.

## Key props

| Prop | Type | Notes |
|------|------|-------|
| `src` | string | Image URL |
| `alt` | string | **Required** for accessibility |
| `name` | string | Auto-initials when no src |
| `color` | string | "initials" for auto from name |
| `size` | "xs"\..."xl" \| number | Size |
| `radius` | "xs"\..."xl" \| number | Circle or rounded |
| `allowedInitialsColors` | string[] | Palette for auto color |

## Rules

- Shows initials from `name` when no `src`.
- `color="initials"` picks color deterministically from name.
- **Avatar.Group** children must be direct Avatar elements — no wrappers.
- Always set `alt` for accessibility.

## Example

```tsx
<Group>
  <Avatar src={user.avatar} alt={user.name} name={user.name} color="initials" />
  <Avatar name="Jane Doe" color="blue" />
  <Avatar.Group>
    <Avatar src="/1.jpg" alt="User 1" />
    <Avatar src="/2.jpg" alt="User 2" />
    <Avatar>+3</Avatar>
  </Avatar.Group>
</Group>
```
