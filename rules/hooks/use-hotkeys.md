# useHotkeys

**Пакет:** `@mantine/hooks`  
**Назначение:** Глобальные сочетания клавиш. Для element-scoped — `getHotkeyHandler`.

## API

```tsx
useHotkeys(hotkeys, tagsToIgnore?, triggerOnContentEditable?);

// hotkeys — массив кортежей [shortcut, handler]
// tagsToIgnore — default ['INPUT', 'TEXTAREA', 'SELECT']
```

## Формат shortcuts

- `mod+K` — ⌘+K на Mac, Ctrl+K на Windows
- `ctrl+shift+X`, `alt+Enter` — несколько модификаторов
- `ArrowLeft`, `Digit1` — специальные клавиши (MDN Key Values)

## Правила

- `mod` — кросс-платформенный модификатор
- `tagsToIgnore` — не срабатывать при фокусе на form-элементах. Пустой массив `[]` — срабатывать везде
- Глобальные shortcuts — `useHotkeys`. Локальные на элементе — `getHotkeyHandler` на `onKeyDown`
- `HotkeyItemOptions`: `preventDefault`, `usePhysicalKeys` (для не-QWERTY раскладок)

## Пример

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
