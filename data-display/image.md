---
description: Mantine Image — image with optional fallback. Set alt for accessibility.
---

# Image

## Purpose

Image component with optional fallback on load error.

## Key props

| Prop | Type | Notes |
|------|------|-------|
| `src` | string | Image URL |
| `alt` | string | **Required** for accessibility |
| `fallbackSrc` | string | Shown on load error |
| `fit` | "contain" \| "cover" \| "fill" \| ... | object-fit |
| `radius` | "xs"\..."xl" \| number | Corner radius |
| `h` \| `w` | string \| number | Dimensions |
| `onError` | handler | Custom error handling |

## Rules

- **Always set `alt`** for accessibility.
- Set `h` (height) to prevent layout shift during load.
- `fallbackSrc` is shown when `src` fails to load.
- For Next.js Image: `component={NextImage}`.
- With `fit="contain"`, usually set `w="auto"` to avoid stretching.

## Example

```tsx
<Image
  src="/hero.jpg"
  alt="Travel destination landscape"
  fallbackSrc="/placeholder.svg"
  h={300}
  radius="md"
  fit="cover"
/>
```
