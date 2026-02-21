# useMediaQuery

**Package:** `@mantine/hooks`
Subscribe to media query (window.matchMedia). **NOT SSR-safe!**

## API

```tsx
const matches = useMediaQuery(query, initialValue?, options?);

// options
{ getInitialValueInEffect?: boolean }  // false — use initialValue on first render
```

## Rules

- **SSR:** Returns `false` (or `initialValue`) on server. Causes hydration mismatch in Next.js when server and client values differ
- **Use ONLY** in client-only UI: Tooltip props, Modal size, etc. Not for responsive layout
- For responsive layout use CSS: `hiddenFrom`/`visibleFrom`, responsive style props, breakpoints in CSS modules
- `initialValue` + `getInitialValueInEffect: false` mitigates SSR issues, but mismatch is still possible
- For Mantine breakpoints use `em()` from `@mantine/core`: `em(768)` → `(max-width: 48em)`

## Example (safe usage)

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
