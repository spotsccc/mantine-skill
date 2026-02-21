# Mantine Hooks (@mantine/hooks)

## Decision tree

| Need | Hook |
|------|------|
| Boolean state (open/close/toggle) | [useDisclosure](use-disclosure.md) |
| Debounce input value | [useDebouncedValue](use-debounced-value.md) |
| Respond to viewport width | [useMediaQuery](use-media-query.md) — **NOT SSR-safe with Next.js!** |
| Detect click outside element | [useClickOutside](use-click-outside.md) |
| Observe element visibility | [useIntersection](use-intersection.md) |
| Keyboard shortcuts | [useHotkeys](use-hotkeys.md) |

## Common patterns

- **useDisclosure** — modals, drawers, burger menus, collapse panels
- **useDebouncedValue** — search inputs (avoid unnecessary API calls)
- **useMediaQuery** — **NOT SSR-safe** → hydration mismatch in Next.js. Only for client-only components (Tooltip props, Modal size). For responsive layout use CSS approaches: `hiddenFrom`/`visibleFrom`, responsive style props, CSS modules with breakpoints.

**Important:** Prefer CSS-based responsive solutions over useMediaQuery in SSR applications.

## Other useful hooks

| Hook | Purpose |
|------|---------|
| useViewportSize, useElementSize, useResizeObserver | Viewport/element dimensions |
| useLocalStorage, useSessionStorage | Persist state |
| useScrollIntoView | Smooth scroll |
| useDebouncedCallback, useThrottledCallback | Throttle/debounce functions |
| useHover | Hover state |
| useMergedRef | Merge multiple refs |
| useId | Stable unique ID |
| usePagination | Pagination logic |

Documentation: https://mantine.dev/hooks/

## Files

| Hook | File |
|------|------|
| useDisclosure | [use-disclosure.md](use-disclosure.md) |
| useDebouncedValue | [use-debounced-value.md](use-debounced-value.md) |
| useMediaQuery | [use-media-query.md](use-media-query.md) |
| useClickOutside | [use-click-outside.md](use-click-outside.md) |
| useIntersection | [use-intersection.md](use-intersection.md) |
| useHotkeys | [use-hotkeys.md](use-hotkeys.md) |
