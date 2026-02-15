# useMediaQuery

**Пакет:** `@mantine/hooks`  
**Назначение:** Подписка на media query (window.matchMedia). **Не SSR-safe!**

## API

```tsx
const matches = useMediaQuery(query, initialValue?, options?);

// options
{ getInitialValueInEffect?: boolean }  // false — использовать initialValue на первом рендере
```

## Правила

- **SSR:** на сервере возвращает `false` (или `initialValue`). Вызывает hydration mismatch в Next.js при разных значениях на сервере и клиенте
- **Использовать ТОЛЬКО** в client-only UI: Tooltip props, Modal size и т.п. Не для responsive layout
- Для responsive layout — CSS: `hiddenFrom`/`visibleFrom`, responsive style props, breakpoints в CSS modules
- `initialValue` + `getInitialValueInEffect: false` смягчает SSR, но mismatch всё равно возможен
- Для breakpoints Mantine использовать `em()` из `@mantine/core`: `em(768)` → `(max-width: 48em)`

## Пример (безопасное использование)

```tsx
'use client';

import { useMediaQuery } from '@mantine/hooks';
import { Tooltip } from '@mantine/core';

function ResponsiveTooltip() {
  const isSmall = useMediaQuery('(max-width: 48em)');

  return (
    <Tooltip
      label="Hint"
      disabled={isSmall}
      multiline={!isSmall}
    >
      <span>Hover me</span>
    </Tooltip>
  );
}
```
