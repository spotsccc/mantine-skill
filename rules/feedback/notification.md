# Notification

**Purpose:** Toast notification. Use the notification system for toasts — not the component directly.

## Key props (Notification component)

| Prop | Type | Description |
|------|------|-------------|
| `title` | string | Bold heading |
| `color` | MantineColor | Theme color key |
| `icon` | ReactNode | Icon left of content |
| `loading` | boolean | Replaces icon with Loader |
| `withCloseButton` | boolean | Default true |
| `onClose` | () => void | Called when close clicked |
| `radius` | MantineRadius | Corner radius |
| `closeButtonProps` | object | Props passed to close button |

## Notification system

```tsx
import { notifications } from '@mantine/notifications';

// Show toast
const id = notifications.show({
  title: 'Saved',
  message: 'Changes applied',
  color: 'green',
  icon: <IconCheck />,
  autoClose: 4000,
  position: 'top-right',
});

notifications.update(id, { message: 'Updated text', loading: false });
notifications.hide(id);
```

## Rules and gotchas

- **Use system:** Add `<Notifications position="top-right" />` to app root. Use `notifications.show()`, not `<Notification />` directly.
- **ID:** `notifications.show()` returns id for `update` / `hide`.
- **Loading:** `loading: true` replaces icon with Loader; update with `loading: false` when done.
- **Auto close:** `autoClose` in ms (default 4000). Set `false` to disable.

## Example

```tsx
import { notifications } from '@mantine/notifications';

const id = notifications.show({
  title: 'Sending...',
  message: 'Please wait',
  loading: true,
  autoClose: false,
});
// later:
notifications.update(id, { message: 'Done!', color: 'green', loading: false, autoClose: 3000 });
```
