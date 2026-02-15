# Button

**Purpose:** Action trigger (button or link-style navigation).

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `variant` | string | `"filled"` \| `"outline"` \| `"light"` \| `"subtle"` \| `"transparent"` \| `"gradient"` \| `"default"` \| `"white"` |
| `color` | MantineColor | Theme color key |
| `size` | MantineSize | `"xs"`–`"xl"` or `"compact-xs"`–`"compact-xl"` |
| `radius` | MantineRadius | Corner radius |
| `fullWidth` | boolean | Stretch to container width |
| `loading` | boolean | Show Loader, disable pointer-events |
| `leftSection` / `rightSection` | ReactNode | Icon or content |
| `justify` | `"left"` \| `"center"` \| `"right"` | Content alignment |
| `gradient` | GradientObject | Required when `variant="gradient"` |
| `component` | Polymorphic | e.g. `component={Link}` for navigation |

## Rules and gotchas

- **Polymorphic:** Use `component={Link}` for Next.js navigation.
- **Disabled on `<a>`:** `disabled` does not work on anchor tags. Use `data-disabled` + `event.preventDefault()` in `onClick`.
- **Tooltip on disabled:** Wrap in Tooltip and set `data-disabled` on Button so Tooltip stays active.
- **Button.Group:** Children must be direct `Button` elements (no wrappers).
- **Compact sizes:** `compact-xs` to `compact-xl` for dense UI.
- `loading` disables pointer-events and shows Loader automatically.

## Example

```tsx
<Button variant="filled" loading={isSubmitting} leftSection={<IconSend />}>
  Отправить
</Button>

<Button component={Link} href="/back">
  Назад
</Button>
```
