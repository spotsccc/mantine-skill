# useDebouncedValue

**Пакет:** `@mantine/hooks`  
**Назначение:** Debounce изменения значения. Для controlled inputs (value prop).

## API

```tsx
const [debounced, cancel] = useDebouncedValue(value, wait, options?);

// options
{ leading?: boolean }  // true — обновить сразу при первом изменении
```

## Правила

- Использовать для search inputs — избежать лишних API-вызовов
- `cancel()` — отменяет ожидающий debounce
- `leading: true` — мгновенное обновление при первом изменении
- Возвращает debounced value (не setter). Значение контролируется родителем
- Отличается от `useDebouncedState`: даёт доступ к «сырому» значению, работает с props и controlled components

## Пример

```tsx
import { useState, useEffect } from 'react';
import { useDebouncedValue } from '@mantine/hooks';
import { TextInput } from '@mantine/core';

function SearchInput() {
  const [value, setValue] = useState('');
  const [debounced] = useDebouncedValue(value, 300);

  useEffect(() => {
    if (!debounced) return;
    fetchResults(debounced);
  }, [debounced]);

  return (
    <TextInput
      value={value}
      onChange={(e) => setValue(e.currentTarget.value)}
      placeholder="Search..."
    />
  );
}
```
