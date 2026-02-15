---
description: Mantine ThemeIcon — icon with colored background. Use for decorative icons alongside text.
---

# ThemeIcon

## Purpose

Icon with colored background. Use for decorative icons alongside text (e.g. feature lists).

## Key props

| Prop | Type | Notes |
|------|------|-------|
| `variant` | "filled" \| "light" \| "outline" \| "gradient" \| "subtle" \| "default" \| "white" | Background style |
| `color` | string | Theme color |
| `size` | "xs"\..."xl" \| number | Container size |
| `radius` | "xs"\..."xl" \| number | Corner radius |
| `gradient` | object | For variant="gradient" |
| `autoContrast` | boolean | Adjust icon contrast |

## Rules

- `size` controls **container** size; set icon size separately (e.g. `size="sm"` on Icon).
- Supports all Mantine color variants.
- Use for decorative icons, not standalone action buttons (use ActionIcon for that).

## Example

```tsx
<Group>
  <ThemeIcon variant="light" color="blue" size="lg" radius="md">
    <IconCheck size={18} />
  </ThemeIcon>
  <ThemeIcon variant="filled" color="green" size="md">
    <IconStar size={14} />
  </ThemeIcon>
</Group>
```
