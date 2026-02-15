# Best Practices

## Styling priority (most preferred first)

1. **Component props** (`color`, `variant`, `size`, `radius`) — control multiple CSS properties at once
2. **Style props** (`c`, `p`, `m`, `bg`, `fz`, `fw`, `ta`, `w`, `h`) — single CSS property each, max 3-4 per component
3. **CSS Modules + `classNames`** — best for complex styles, pseudo-classes, media queries
4. **`style` prop** — last resort, only for values not available as props

## Do NOT use `style={{...}}` for theme values

```tsx
// BAD
<Box style={{ padding: 16, color: 'blue', borderRadius: 8 }} />

// GOOD
<Box p="md" c="blue" style={{ borderRadius: 'var(--mantine-radius-md)' }} />

// BEST (if only theme values)
<Box p="md" c="blue" />
```

Common replacements:

| Instead of `style={{...}}` | Use prop |
|---------------------------|----------|
| `padding: 16` | `p="md"` or `p={16}` |
| `margin: 8` | `m="xs"` |
| `color: 'red'` | `c="red"` |
| `backgroundColor: '...'` | `bg="gray.1"` |
| `fontSize: 14` | `fz="sm"` |
| `fontWeight: 700` | `fw={700}` |
| `textAlign: 'center'` | `ta="center"` |
| `width: '100%'` | `w="100%"` |
| `height: 200` | `h={200}` |
| `maxWidth: 600` | `maw={600}` |
| `display: 'flex'` | `display="flex"` |
| `position: 'relative'` | `pos="relative"` |

## Style props with theme values

```tsx
// Spacing: xs, sm, md, lg, xl
<Box p="md" m="lg" />

// Colors: "colorName" or "colorName.shade"
<Text c="blue">Primary shade</Text>
<Text c="blue.3">Specific shade</Text>
<Text c="dimmed">Dimmed text (auto light/dark)</Text>

// Special color values
<Box bg="var(--mantine-color-body)">Body background</Box>
```

## Styles API (inner elements)

Use `classNames` (NOT `styles`) to style inner elements of Mantine components:

```tsx
// GOOD — CSS Modules + classNames
import classes from './MyInput.module.css';
<TextInput classNames={{ root: classes.root, input: classes.input, label: classes.label }} />

// AVOID — styles prop (inline, hard to override)
<TextInput styles={{ input: { backgroundColor: 'red' } }} />
```

For custom component sizes, use `vars` resolver:

```tsx
Button.extend({
  vars: (theme, props) => {
    if (props.size === 'xxl') {
      return { root: { '--button-height': '60px', '--button-fz': '24px' } };
    }
    return { root: {} };
  },
})
```

## Default props

Define reusable component defaults via theme:

```tsx
const theme = createTheme({
  components: {
    Button: Button.extend({
      defaultProps: { variant: 'outline', radius: 'md' },
    }),
  },
});
```

Or with `withProps` for one-off variants:

```tsx
const PrimaryButton = Button.withProps({ variant: 'filled', color: 'blue' });
```

## Responsive design

### Conditional rendering (SSR-safe)

```tsx
<Image visibleFrom="md" src="/desktop.jpg" />
<Image hiddenFrom="md" src="/mobile.jpg" />
```

### Responsive style props (use sparingly — injects `<style>` tag per component)

```tsx
<Box w={{ base: '100%', sm: '50%', lg: '33%' }} p={{ base: 'sm', md: 'xl' }} />
```

**Do NOT use responsive style props in large lists** — each item creates a `<style>` tag.

### CSS Modules + PostCSS mixins (best for complex responsive)

```scss
.card {
  padding: var(--mantine-spacing-sm);

  @mixin larger-than $mantine-breakpoint-md {
    padding: var(--mantine-spacing-xl);
  }
}
```

### Component responsive props

Grid, SimpleGrid use responsive object syntax directly (same `<style>` injection caveat):

```tsx
<SimpleGrid cols={{ base: 1, sm: 2, lg: 4 }} />
<Grid.Col span={{ base: 12, md: 6 }} />
```

## PostCSS preset (`postcss-preset-mantine`)

Available functions and mixins in `.module.css` files:

| Feature | Syntax | Purpose |
|---------|--------|---------|
| `rem()` | `font-size: rem(16px)` | Convert px to rem |
| `em()` | `@media (min-width: em(768px))` | Convert px to em (media queries) |
| `light-dark()` | `color: light-dark(black, white)` | Color scheme values |
| `@mixin hover` | `@mixin hover { color: red; }` | Hover with touch fallback |
| `@mixin light` | `@mixin light { ... }` | Light scheme only |
| `@mixin dark` | `@mixin dark { ... }` | Dark scheme only |
| `@mixin smaller-than` | `@mixin smaller-than $mantine-breakpoint-sm { ... }` | Max-width media |
| `@mixin larger-than` | `@mixin larger-than $mantine-breakpoint-md { ... }` | Min-width media |
| `alpha()` | `color: alpha(var(--mantine-color-red-4), 0.5)` | Add transparency |

## Polymorphic components

```tsx
// Next.js Link (v13+)
<Button component={Link} href="/about">About</Button>

// For generic components, use renderRoot
<Button renderRoot={(props) => <Link {...props} href="/about" />}>About</Button>
```

## Performance summary

| Approach | Performance | When to use |
|----------|------------|-------------|
| CSS Modules | Best | Complex styles, pseudo-classes, media queries |
| Component props | Best | Color, variant, size, radius |
| Style props (static) | Good | 1-3 simple properties |
| style prop | Good | One-off non-theme values |
| Responsive style props | Moderate | Few components, NOT in lists |
| styles prop | Avoid | Prefer classNames instead |

## CSS Variables reference

```scss
// Spacing
var(--mantine-spacing-xs)  // 0.625rem
var(--mantine-spacing-sm)  // 0.75rem
var(--mantine-spacing-md)  // 1rem
var(--mantine-spacing-lg)  // 1.25rem
var(--mantine-spacing-xl)  // 1.5rem

// Colors
var(--mantine-color-blue-6)
var(--mantine-color-dimmed)         // auto light/dark
var(--mantine-color-body)           // page background
var(--mantine-primary-color-filled) // primary filled color

// Typography
var(--mantine-font-size-sm)
var(--mantine-font-family)
var(--mantine-font-family-headings)

// Radius
var(--mantine-radius-sm)
var(--mantine-radius-default)       // theme.defaultRadius

// z-index
var(--mantine-z-index-modal)  // 200
var(--mantine-z-index-popover) // 300
```
