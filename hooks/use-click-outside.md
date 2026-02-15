# useClickOutside

**Пакет:** `@mantine/hooks`  
**Назначение:** Обработка клика вне элемента.

## API

```tsx
const ref = useClickOutside(handler, events?, nodes?);

// events — массив событий, по умолчанию ['mousedown', 'touchstart']
// nodes — массив refs элементов, которые не считаются "outside"
```

## Правила

- Возвращаемый `ref` вешать на элемент, внутри которого клик считается «внутренним»
- `nodes` — дополнительные refs, клик по которым не триггерит handler (например, dropdown + button). Для множественных узлов использовать `useState` для refs, т.к. `useRef` не даёт актуальные элементы при порталах
- Порядок: `handler`, `events` (или `null` для default), `nodes`

## Пример

```tsx
import { useState } from 'react';
import { useClickOutside } from '@mantine/hooks';
import { Box, Button } from '@mantine/core';

function CustomDropdown() {
  const [opened, setOpened] = useState(false);
  const ref = useClickOutside(() => setOpened(false));

  return (
    <>
      <Button onClick={() => setOpened(true)}>Open</Button>
      {opened && (
        <Box ref={ref} p="md" bg="gray.1">
          Click outside to close
        </Box>
      )}
    </>
  );
}
```
