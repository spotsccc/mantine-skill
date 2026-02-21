# Popover

**Purpose:** Positioned popup anchored to target element. Forms, rich dropdowns, contextual UI.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `opened` / `onChange` | boolean | Controlled state |
| `position` | PopoverPosition | Placement |
| `width` | "target" \| number | "target" matches trigger width |
| `offset` | number | Distance from target |
| `withArrow` | boolean | Show arrow |
| `arrowSize` | number | Arrow dimensions |
| `trapFocus` | boolean | Focus management |
| `withinPortal` | boolean | Default true |
| `closeOnClickOutside` | boolean | Default true |
| `closeOnEscape` | boolean | Default true |
| `middlewares` | object | `{ flip, shift, inline }` |

## Compound components

- **Popover.Target** — trigger element (child MUST support ref)
- **Popover.Dropdown** — popup content

## Rules and gotchas

- Uncontrolled (click to toggle) by default
- **Popover.Target child MUST support ref** (button, div, span)
- `width="target"` makes dropdown match target width
- Nested dropdowns (Select inside Popover): `withinPortal={false}` on inner
- `trapFocus` for focus management when dropdown has interactive content

## Example

```tsx
<Popover width="target" trapFocus>
  <Popover.Target>
    <Button>Open</Button>
  </Popover.Target>
  <Popover.Dropdown>
    <TextInput label="Name" placeholder="Enter..." />
    <Select label="Role" data={roles} />
    <Button fullWidth mt="sm">Save</Button>
  </Popover.Dropdown>
</Popover>
```
