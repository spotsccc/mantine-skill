# useHotkeys

**Package:** `@mantine/hooks`
Global keyboard shortcuts. For element-scoped use `getHotkeyHandler`.

## API

```tsx
useHotkeys(hotkeys, tagsToIgnore?, triggerOnContentEditable?);

// hotkeys — array of tuples [shortcut, handler]
// tagsToIgnore — default ['INPUT', 'TEXTAREA', 'SELECT']
```

## Shortcut format

- `mod+K` — ⌘+K on Mac, Ctrl+K on Windows
- `ctrl+shift+X`, `alt+Enter` — multiple modifiers
- `ArrowLeft`, `Digit1` — special keys (MDN Key Values)

## Rules

- `mod` — cross-platform modifier
- `tagsToIgnore` — don't fire when focused on form elements. Empty array `[]` — fire everywhere
- Global shortcuts — `useHotkeys`. Element-scoped — `getHotkeyHandler` on `onKeyDown`
- `HotkeyItemOptions`: `preventDefault`, `usePhysicalKeys` (for non-QWERTY layouts)

## Example

```tsx
import { useHotkeys, useDisclosure } from '@mantine/hooks';

function App() {
  const [searchOpened, { open, close, toggle }] = useDisclosure(false);

  useHotkeys([['mod+K', toggle]]);

  return (
    <>
      <Button onClick={open}>
        Search (Ctrl+K)
      </Button>
      <Modal opened={searchOpened} onClose={close}>
        <SearchInput />
      </Modal>
    </>
  );
}
```
