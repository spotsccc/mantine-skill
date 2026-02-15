# Group

**Purpose:** Horizontal flex container.

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `gap` | MantineSpacing | Horizontal spacing |
| `justify` | JustifyContent | Main axis alignment |
| `align` | AlignItems | Cross axis alignment |
| `grow` | boolean | Children grow to fill space |
| `wrap` | FlexWrap | Wrap behavior |
| `preventGrowOverflow` | boolean | Limit children to `(1/N)*100%` width (default `true`) |

## Rules and gotchas

- Horizontal only — use `Stack` for vertical.
- Works only with React elements — NOT strings, numbers, or fragments as direct children.
- `preventGrowOverflow` limits each child to `(1/N)*100%` when `grow` is true, preventing overflow.
- Not polymorphic.

## Example

```tsx
<Group justify="space-between">
  <Logo />
  <Nav />
</Group>

<Group gap="sm" grow>
  <Button>Save</Button>
  <Button variant="light">Cancel</Button>
</Group>
```
