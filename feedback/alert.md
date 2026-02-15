# Alert

**Purpose:** Static important message block (success, warning, error, info). Stays in layout.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `title` | string | Bold heading above message |
| `icon` | ReactNode | Icon to the left (e.g. `<IconAlertCircle />`) |
| `color` | MantineColor | Theme color key |
| `variant` | string | `"filled"` \| `"light"` \| `"outline"` \| `"transparent"` \| `"white"` \| `"default"` |
| `withCloseButton` | boolean | Show close button |
| `onClose` | () => void | Called when close clicked |
| `closeButtonLabel` | string | aria-label for close (required when `withCloseButton`) |
| `radius` | MantineRadius | Corner radius |

## Rules and gotchas

- **Accessibility:** `withCloseButton` needs `closeButtonLabel` for screen readers.
- **Use case:** Not for toast notifications — use Notification system instead.
- **Layout:** `icon` appears left of content.
- Static content — stays in DOM until user closes or state changes.

## Example

```tsx
<Alert
  title="Ошибка сохранения"
  icon={<IconAlertCircle />}
  color="red"
  variant="light"
  withCloseButton
  closeButtonLabel="Закрыть"
  onClose={() => setShow(false)}
>
  Не удалось сохранить изменения. Попробуйте ещё раз.
</Alert>
```
