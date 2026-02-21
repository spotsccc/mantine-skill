# Modal

**Purpose:** Accessible overlay dialog for confirmations, forms, and focused content.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `opened` | boolean | **Required.** Visibility state |
| `onClose` | () => void | **Required.** Called on close |
| `title` | ReactNode | Header text |
| `size` | "xs" \| "sm" \| "md" \| "lg" \| "xl" \| "auto" \| number \| "100%" | Width |
| `centered` | boolean | Vertical centering |
| `fullScreen` | boolean | Full viewport |
| `withCloseButton` | boolean | Default true |
| `trapFocus` | boolean | Default true |
| `closeOnEscape` | boolean | Default true |
| `closeOnClickOutside` | boolean | Default true |
| `overlayProps` | object | Overlay styling |
| `transitionProps` | object | Transition config |
| `keepMounted` | boolean | Keep DOM when closed |
| `withinPortal` | boolean | Default true |

## Compound components

`Modal.Header`, `Modal.Title`, `Modal.Body`, `Modal.CloseButton`, `Modal.Content`, `Modal.Overlay`, `Modal.Root` — use for custom layout (skip title/header if needed).

## Rules and gotchas

- **ALWAYS use `useDisclosure`** for state
- `fullScreen` for mobile modals
- `centered` for vertical centering
- `keepMounted` preserves form state when closed
- `size="auto"` fits content width

## Example

```tsx
const [opened, { open, close }] = useDisclosure();

<Modal opened={opened} onClose={close} title="Confirmation" centered>
  <Text>Are you sure?</Text>
  <Group mt="md" justify="flex-end">
    <Button variant="subtle" onClick={close}>Cancel</Button>
    <Button onClick={handleConfirm}>OK</Button>
  </Group>
</Modal>

<Button onClick={open}>Open</Button>
```
