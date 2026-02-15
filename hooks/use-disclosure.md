# useDisclosure

**Пакет:** `@mantine/hooks`  
**Назначение:** Boolean state с handlers open/close/toggle.

## API

```tsx
const [opened, { open, close, toggle }] = useDisclosure(initialState?, callbacks?);

// callbacks
{ onOpen?: () => void; onClose?: () => void; }
```

## Правила

- Предпочитать вместо `useState` для boolean open/close state
- Совместим с Modal `opened`/`onClose`, Drawer, Popover, Collapse, Burger
- `toggle` — один handler для переключения
- `open`/`close` — явное управление
- Callbacks `onOpen`/`onClose` вызываются при смене состояния; `open`/`close` ничего не делают, если состояние уже совпадает

## Пример

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
