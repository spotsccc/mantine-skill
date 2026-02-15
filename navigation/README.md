# Navigation Components

## Decision tree

- **Sidebar link with icon/description** → [NavLink](nav-link.md)
- **Path breadcrumbs** → [Breadcrumbs](breadcrumbs.md)
- **Mobile menu toggle** → [Burger](burger.md) (with useDisclosure)
- **Dropdown actions menu** → [Menu](menu.md)
- **Content tabs** → [Tabs](tabs.md)
- **Page navigation** → [Pagination](pagination.md)
- **Multi-step wizard** → [Stepper](stepper.md)

## Common patterns

- **NavLink** supports nested links (accordion-style) via children
- **Burger + useDisclosure** for mobile nav toggle state
- **Menu.Target** must be a button for accessibility (keyboard focus)
- **Tabs** is compound: `Tabs.List`, `Tabs.Tab`, `Tabs.Panel`

## Components

| Component | File | Purpose |
|-----------|------|---------|
| NavLink | [nav-link.md](nav-link.md) | Sidebar link with icon, description, nested accordion |
| Breadcrumbs | [breadcrumbs.md](breadcrumbs.md) | Path navigation breadcrumbs |
| Burger | [burger.md](burger.md) | Mobile menu toggle (hamburger ↔ close) |
| Menu | [menu.md](menu.md) | Dropdown action menu |
| Tabs | [tabs.md](tabs.md) | Content tab switching |
| Pagination | [pagination.md](pagination.md) | Page number navigation |
| Stepper | [stepper.md](stepper.md) | Multi-step wizard / progress |
