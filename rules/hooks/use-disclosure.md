# useDisclosure

**Package:** `@mantine/hooks`
Boolean state with open/close/toggle handlers.

## API

```tsx
const [opened, { open, close, toggle }] = useDisclosure(initialState?, callbacks?);

// callbacks
{ onOpen?: () => void; onClose?: () => void; }
```

## Rules

- Prefer over `useState` for boolean open/close state
- Compatible with Modal `opened`/`onClose`, Drawer, Popover, Collapse, Burger
- `toggle` — single handler for toggling
- `open`/`close` — explicit control
- Callbacks `onOpen`/`onClose` fire on state change; `open`/`close` are no-ops if state already matches

## Example

```tsx
import { useDisclosure } from '@mantine/hooks';
import { Modal, Button } from '@mantine/core';

function Demo() {
  const [opened, { open, close }] = useDisclosure(false);

  return (
    <>
      <Modal opened={opened} onClose={close} title="Example">
        Content
      </Modal>
      <Button onClick={open}>Open modal</Button>
    </>
  );
}
```
