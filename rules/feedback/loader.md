# Loader

**Purpose:** Spinning loading indicator. Inline or inside buttons/containers.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `type` | string | `"oval"` \| `"bars"` \| `"dots"` |
| `size` | MantineSize \| number | `"xs"`–`"xl"` or pixel value |
| `color` | MantineColor | Theme color key |

## Rules and gotchas

- **Defaults:** Type and color inherit from theme.
- **Custom styling:** Use CSS variables `--loader-size` and `--loader-color` for custom loaders.
- **Children:** Pass `children` to replace default loader with custom content.
- Common use: inside Button (`loading` prop) or LoadingOverlay.
- Inline only — for full-block blocking use LoadingOverlay.

## Example

```tsx
<Loader type="oval" size="lg" color="blue" />

<Group>
  <Loader type="bars" size="sm" />
  <Text>Loading...</Text>
</Group>
```
