# LoadingOverlay

**Purpose:** Semi-transparent overlay that blocks UI during loading. Covers parent area with Loader.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `visible` | boolean | Show/hide overlay |
| `loaderProps` | object | Props passed to Loader (type, size, color) |
| `overlayProps` | object | Props passed to overlay Box |
| `zIndex` | number | Stack order (default from theme) |

## Rules and gotchas

- **Parent:** Parent element MUST have `position: relative`. Use `pos="relative"` on Box/Paper.
- **Focus:** Overlay content remains keyboard-focusable (useful for forms).
- **Use for:** Forms, cards, sections being loaded — when entire block is inactive.
- Not for inline spinners — use Loader instead.

## Example

```tsx
<Box pos="relative">
  <LoadingOverlay visible={isLoading} loaderProps={{ type: 'oval', size: 'lg' }} />
  <Paper p="md">
    <TextInput label="Email" />
    <Button mt="md">Submit</Button>
  </Paper>
</Box>
```
