# Menu

**Purpose:** Dropdown action menu (actions, options, context menu).

## Key props (Menu)

| Prop | Type | Description |
|------|------|-------------|
| `opened` / `onChange` | boolean | Controlled open state |
| `trigger` | `"click"` \| `"hover"` \| `"click-hover"` | Open trigger |
| `position` | PopoverPosition | Placement |
| `width` | number \| string | Dropdown width |
| `closeOnItemClick` | boolean | Default true |
| `openDelay` / `closeDelay` | number | For hover trigger |

## Compound structure

- **Menu.Target** — trigger element (must be button)
- **Menu.Dropdown** — dropdown container
- **Menu.Item** — menu item
- **Menu.Label** — section label
- **Menu.Divider** — separator

## Rules and gotchas

- **Menu.Target must be a button** — for keyboard accessibility
- `trigger="hover"` is NOT keyboard accessible — prefer `trigger="click-hover"`
- Destructive actions: `Menu.Item color="red"`
- Menu.Item supports `leftSection`, `rightSection`, `disabled`

## Example

```tsx
<Menu>
  <Menu.Target>
    <Button variant="subtle">Actions</Button>
  </Menu.Target>
  <Menu.Dropdown>
    <Menu.Label>Account</Menu.Label>
    <Menu.Item leftSection={<IconUser />}>Profile</Menu.Item>
    <Menu.Divider />
    <Menu.Item color="red" leftSection={<IconLogout />}>
      Logout
    </Menu.Item>
  </Menu.Dropdown>
</Menu>
```
