# useIntersection

**Package:** `@mantine/hooks`
IntersectionObserver — observe element intersection with viewport/container.

## API

```tsx
const { ref, entry } = useIntersection(options?);

// options — IntersectionObserverInit
{ root?, rootMargin?, threshold? }
```

## Rules

- Pass `ref` to the observed element
- `entry?.isIntersecting` — element is visible
- Suitable for infinite scroll, lazy loading, scroll-spy
- `threshold` — number 0–1 or array for partial visibility
- On first render and during SSR `entry === null`

## Example (lazy loading)

```tsx
import { useState, useEffect } from 'react';
import { useIntersection } from '@mantine/hooks';
import { Skeleton } from '@mantine/core';

function LazySection() {
  const { ref, entry } = useIntersection({ threshold: 0.1 });
  const [loaded, setLoaded] = useState(false);

  useEffect(() => {
    if (entry?.isIntersecting && !loaded) {
      setLoaded(true);
      loadHeavyContent();
    }
  }, [entry?.isIntersecting, loaded]);

  return <div ref={ref}>{loaded ? <HeavyContent /> : <Skeleton />}</div>;
}
```
