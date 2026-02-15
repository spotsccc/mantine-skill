# useIntersection

**Пакет:** `@mantine/hooks`  
**Назначение:** IntersectionObserver — пересечение элемента с viewport/контейнером.

## API

```tsx
const { ref, entry } = useIntersection(options?);

// options — IntersectionObserverInit
{ root?, rootMargin?, threshold? }
```

## Правила

- `ref` передавать наблюдаемому элементу
- `entry?.isIntersecting` — элемент виден
- Подходит для infinite scroll, lazy loading, scroll-spy
- `threshold` — число 0–1 или массив для частичной видимости
- На первом рендере и при SSR `entry === null`

## Пример (lazy loading)

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
