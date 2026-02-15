# Breadcrumbs

**Purpose:** Path navigation breadcrumbs (e.g. Home / Category / Page).

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `separator` | ReactNode | Default `"/"` |
| `separatorMargin` | MantineSpacing | Gap around separator |
| `children` | ReactNode[] | Array of Anchor/Text elements |

## Rules and gotchas

- Pass array of `Anchor` or `Text` as children
- Last item typically plain `Text` (not a link) — current page
- `separator` can be any ReactNode (icon, custom component)

## Example

```tsx
<Breadcrumbs separator="/">
  <Anchor href="/">Home</Anchor>
  <Anchor href="/articles">Articles</Anchor>
  <Text c="dimmed">Current Article</Text>
</Breadcrumbs>
```
