# Drawer

**Purpose:** Side panel overlay sliding from viewport edge. Filters, settings, detail views.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `opened` | boolean | **Required.** Visibility state |
| `onClose` | () => void | **Required.** Called on close |
| `position` | "left" \| "right" \| "top" \| "bottom" | Slide direction |
| `size` | MantineSize \| number \| string | Width (L/R) or height (T/B) |
| `title` | ReactNode | Header text |
| `offset` | number | Gap from viewport edge |
| `withCloseButton` | boolean | Default true |
| `closeOnEscape` | boolean | Default true |
| `closeOnClickOutside` | boolean | Default true |
| `overlayProps` | object | Overlay styling |
| `transitionProps` | object | Transition config |

## Rules and gotchas

- **Use `useDisclosure`** for state
- `position` controls which side it slides from
- `size` is width for left/right, height for top/bottom
- `offset` creates gap between drawer and viewport edge
- Same compound components as Modal (Drawer.Header, Drawer.Title, Drawer.Body, etc.)

## Example

```tsx
const [opened, { open, close }] = useDisclosure();

<Drawer opened={opened} onClose={close} title="Filters" position="right" size="md">
  <Stack>
    <TextInput label="Search" placeholder="..." />
    <Select label="Category" data={categories} />
    <Button onClick={close}>Apply</Button>
  </Stack>
</Drawer>

<Button onClick={open}>Filters</Button>
```
