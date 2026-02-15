# ActionIcon

**Purpose:** Icon-only button for compact actions.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `variant` | string | Same as Button |
| `color` | MantineColor | Theme color |
| `size` | MantineSize \| number | `"xs"`–`"xl"`, or `"input-sm"` / `"input-md"` / `"input-lg"` for input alignment |
| `radius` | MantineRadius | Corner radius |
| `loading` | boolean | Show Loader |
| `aria-label` | string | **REQUIRED** — describes action for screen readers |

## Rules and gotchas

- **`aria-label` обязателен** — без него кнопка недоступна для assistive tech.
- Icon size is separate from button size — use `size` prop on Icon to match.
- **`data-disabled`** — для ссылок (`component={Link}`) и Tooltip: `disabled` не работает на `<a>`, используй `data-disabled` + `preventDefault`.
- **ActionIcon.Group** — для сгруппированных иконок с общим gap.
- **`size="input-sm"`** — выравнивает высоту под TextInput/Select.

## Example

```tsx
<ActionIcon variant="subtle" aria-label="Удалить">
  <IconTrash size={18} />
</ActionIcon>

<ActionIcon size="input-md" aria-label="Поиск" loading={isSearching}>
  <IconSearch />
</ActionIcon>
```
