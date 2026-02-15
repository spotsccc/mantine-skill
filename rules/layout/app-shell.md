# AppShell

**Purpose:** Page-level layout with fixed header, navbar, aside, footer.

## Key props

| Prop | Type | Description |
|------|------|--------------|
| `header` | `{ height, collapsed?, offset? }` | Header config |
| `navbar` | `{ width, breakpoint?, collapsed }` | Navbar (collapsed: `{ mobile, desktop }`) |
| `aside` | `{ width, breakpoint?, collapsed }` | Aside panel |
| `footer` | `{ height, collapsed? }` | Footer config |
| `padding` | MantineSpacing | Apply to AppShell, not Main |
| `layout` | `"default"` \| `"alt"` | Layout variant |
| `disabled` | boolean | Hide all sections except Main |
| `withBorder` | boolean | Border between sections |
| `zIndex` | number | Stack order |
| `transitionDuration` | number | Collapse animation ms |

## Compound components

- `AppShell.Header`, `AppShell.Navbar`, `AppShell.Aside`, `AppShell.Footer`, `AppShell.Main`, `AppShell.Section`

## Rules and gotchas

- All sections use `position: fixed` — Main gets padding to avoid overlap.
- Use `padding` on AppShell (NOT `p` on AppShell.Main).
- Navbar/aside `collapsed` is responsive: `{{ mobile: true, desktop: false }}`. Use `useDisclosure` for toggle.
- `AppShell.Section` with `grow` fills remaining space.
- Do NOT use `<main>` inside `AppShell.Main` — it renders as main already.
- `disabled` hides header, navbar, aside, footer; only Main content shows.

## Example

```tsx
const [opened, { toggle }] = useDisclosure();

<AppShell
  header={{ height: 60 }}
  navbar={{ width: 280, breakpoint: 'sm', collapsed: { mobile: !opened, desktop: false } }}
  padding="md"
>
  <AppShell.Header>
    <Burger opened={opened} onClick={toggle} hiddenFrom="sm" />
    <Logo />
  </AppShell.Header>
  <AppShell.Navbar>Nav links</AppShell.Navbar>
  <AppShell.Main>Page content</AppShell.Main>
</AppShell>
```
