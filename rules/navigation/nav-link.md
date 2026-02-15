# NavLink

**Purpose:** Sidebar navigation link with icon and optional description.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `label` | ReactNode | Main text |
| `description` | ReactNode | Secondary text below label |
| `leftSection` / `rightSection` | ReactNode | Icon or content |
| `active` | boolean | Highlights link (current page) |
| `color` | MantineColor | Active/hover color |
| `disabled` | boolean | Disabled state |
| `defaultOpened` | boolean | Accordion open by default |
| `childrenOffset` | MantineSpacing | Indent for nested children |
| `component` | Polymorphic | Default `<a>`, use `Link` for Next.js |

## Rules and gotchas

- **Polymorphic:** Default `<a>`; for Next.js use `component={Link}` with `href`
- **Nested NavLink:** Children create accordion-style sub-navigation
- **Active state:** Set `active={true}` or use React Router (auto from `aria-current`)
- **Accessibility:** Works with `aria-current="page"` for active detection

## Example

```tsx
<NavLink
  label="Dashboard"
  description="Overview"
  leftSection={<IconDashboard />}
  active={pathname === '/dashboard'}
  href="/dashboard"
/>

<NavLink label="Settings" defaultOpened>
  <NavLink label="Profile" href="/settings/profile" />
  <NavLink label="Security" href="/settings/security" />
</NavLink>
```
