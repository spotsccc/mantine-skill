# Skeleton

**Purpose:** Content loading placeholder. Animated rectangle that mimics layout of content being loaded.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `height` | number \| string | Height (px or CSS value) |
| `width` | number \| string | Width (px or CSS value) |
| `radius` | MantineRadius | Corner radius |
| `circle` | boolean | Circular skeleton (e.g. avatar) |
| `animate` | boolean | Default true — shimmer animation |
| `visible` | boolean | Default true — when false, renders children instead |

## Rules and gotchas

- **Dimensions:** Match dimensions of content being loaded for seamless swap.
- **Content swap:** When `visible={false}` renders children — use for loading→content transition.
- **Reduced motion:** Set `animate={false}` if user prefers reduced motion.
- **Circle:** `circle` shorthand for circular skeleton (avatar placeholders).

## Example

```tsx
{loading ? (
  <Stack>
    <Skeleton height={24} width="60%" radius="sm" />
    <Skeleton height={14} width="100%" radius="sm" />
    <Skeleton height={14} width="80%" radius="sm" />
    <Group mt="md">
      <Skeleton height={36} circle />
      <Skeleton height={16} width={120} radius="sm" />
    </Group>
  </Stack>
) : (
  <Article content={data} />
)}
```
