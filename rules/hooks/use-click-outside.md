# useClickOutside

**Package:** `@mantine/hooks`
Handle clicks outside an element.

## API

```tsx
const ref = useClickOutside(handler, events?, nodes?);

// events — event array, defaults to ['mousedown', 'touchstart']
// nodes — array of refs for elements that are not considered "outside"
```

## Rules

- Attach returned `ref` to the element inside which clicks are considered "inside"
- `nodes` — additional refs where clicks don't trigger handler (e.g. dropdown + button). For multiple nodes use `useState` for refs, since `useRef` won't provide current elements with portals
- Parameter order: `handler`, `events` (or `null` for defaults), `nodes`

## Example

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
