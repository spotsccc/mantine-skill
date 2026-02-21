# useDebouncedValue

**Package:** `@mantine/hooks`
Debounce value changes. For controlled inputs (value prop).

## API

```tsx
const [debounced, cancel] = useDebouncedValue(value, wait, options?);

// options
{ leading?: boolean }  // true — update immediately on first change
```

## Rules

- Use for search inputs — avoid unnecessary API calls
- `cancel()` — cancels pending debounce
- `leading: true` — immediate update on first change
- Returns debounced value (not setter). Value is controlled by parent
- Differs from `useDebouncedState`: provides access to raw value, works with props and controlled components

## Example

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
