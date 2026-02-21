# Overlays

## Decision tree

| Need | Component |
|------|-----------|
| Dialog / confirmation | **Modal** |
| Side panel (slide-in) | **Drawer** |
| Anchored popup with rich content | **Popover** |
| Simple text hint on hover | **Tooltip** |
| Preview card on hover | **HoverCard** |

## Common patterns

- **Modal** and **Drawer** use `useDisclosure` for opened/close handlers
- **Popover**, **Tooltip**, **HoverCard** anchor to a Target element
- All overlays render in Portal by default — override with `withinPortal={false}`
- Focus trap enabled by default in Modal, optional in Popover

## Components

| Component | File | Purpose |
|-----------|------|---------|
| Modal | [modal.md](modal.md) | Accessible overlay dialog |
| Drawer | [drawer.md](drawer.md) | Side panel overlay |
| Popover | [popover.md](popover.md) | Anchored popup with rich content |
| Tooltip | [tooltip.md](tooltip.md) | Simple text hint on hover |
| HoverCard | [hover-card.md](hover-card.md) | Rich content preview on hover |
