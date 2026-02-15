# Mantine Hooks (@mantine/hooks)

## Decision tree

| Нужно | Хук |
|-------|-----|
| Boolean state (open/close/toggle) | [useDisclosure](use-disclosure.md) |
| Debounce input value | [useDebouncedValue](use-debounced-value.md) |
| Respond to viewport width | [useMediaQuery](use-media-query.md) — **не SSR-safe с Next.js!** |
| Detect click outside element | [useClickOutside](use-click-outside.md) |
| Observe element visibility | [useIntersection](use-intersection.md) |
| Keyboard shortcuts | [useHotkeys](use-hotkeys.md) |

## Common patterns

- **useDisclosure** — modals, drawers, burger menus, collapse panels
- **useDebouncedValue** — search inputs (избегать лишних API-вызовов)
- **useMediaQuery** — **не SSR-safe** → hydration mismatch в Next.js. Только для client-only компонентов (Tooltip props, Modal size). Для responsive layout — CSS-подходы: `hiddenFrom`/`visibleFrom`, responsive style props, CSS modules с breakpoints.

**Важно:** предпочитать CSS-based responsive решения вместо useMediaQuery в SSR-приложениях.

## Другие полезные хуки

| Хук | Назначение |
|-----|------------|
| useViewportSize, useElementSize, useResizeObserver | Размеры viewport/элемента |
| useLocalStorage, useSessionStorage | Сохранение состояния |
| useScrollIntoView | Плавная прокрутка |
| useDebouncedCallback, useThrottledCallback | Throttling/debounce функции |
| useHover | Состояние hover |
| useMergedRef | Объединение нескольких refs |
| useId | Стабильный уникальный ID |
| usePagination | Логика пагинации |

Документация: https://mantine.dev/hooks/

## Файлы

| Хук | Файл |
|-----|------|
| useDisclosure | [use-disclosure.md](use-disclosure.md) |
| useDebouncedValue | [use-debounced-value.md](use-debounced-value.md) |
| useMediaQuery | [use-media-query.md](use-media-query.md) |
| useClickOutside | [use-click-outside.md](use-click-outside.md) |
| useIntersection | [use-intersection.md](use-intersection.md) |
| useHotkeys | [use-hotkeys.md](use-hotkeys.md) |
