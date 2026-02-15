# Layout Components

## Decision tree

- **Vertical stack of elements** → [Stack](stack.md) (`gap` prop)
- **Horizontal row of elements** → [Group](group.md) (`gap`, `justify`, `wrap`)
- **Full control over flex** → [Flex](flex.md) (responsive `direction`, `wrap`, etc.)
- **Equal-width grid** → [SimpleGrid](simple-grid.md) (`cols` responsive)
- **12-column grid with different spans** → [Grid](grid.md) (`Grid.Col span`)
- **Page-level layout (header/navbar/footer)** → [AppShell](app-shell.md)
- **Max-width centered wrapper** → [Container](container.md) (`size`, `fluid`)
- **Card/surface with background and shadow** → [Paper](paper.md) / [Card](card.md)
- **Center content** → [Center](center.md)
- **Spacing between elements** → [Space](space.md) (prefer `gap` in Stack/Group instead)
- **Horizontal line separator** → [Divider](divider.md)
- **Generic wrapper** → [Box](box.md) (renders `<div>`, no default styles)

## Common patterns

### Stack vs Group vs Flex

| Component | Direction | Polymorphic | Responsive direction |
|-----------|-----------|-------------|---------------------|
| Stack | Vertical only | No | No |
| Group | Horizontal only | No | No |
| Flex | Any | Yes | Yes |

Use `Stack`/`Group` when direction is fixed. Use `Flex` when you need responsive `direction` or polymorphism.

### Grid vs SimpleGrid

| Feature | SimpleGrid | Grid |
|---------|-----------|------|
| Equal columns | Yes | Yes |
| Different column widths | No | Yes (`span`) |
| Column offset/order | No | Yes |
| Container queries | Yes | Yes |
| Performance | Same | Same |

### Paper vs Card

`Card` extends `Paper` with sections support (`Card.Section`). Use `Paper` for simple surfaces, `Card` when you need structured sections with full-bleed content.

## Components

| Component | File | Purpose |
|-----------|------|---------|
| Container | [container.md](container.md) | Max-width centered wrapper |
| Grid | [grid.md](grid.md) | 12-column responsive grid |
| SimpleGrid | [simple-grid.md](simple-grid.md) | Equal-width responsive grid |
| Stack | [stack.md](stack.md) | Vertical flex container |
| Group | [group.md](group.md) | Horizontal flex container |
| Flex | [flex.md](flex.md) | Full-control flex container |
| Box | [box.md](box.md) | Generic wrapper (div) |
| AppShell | [app-shell.md](app-shell.md) | Page-level layout shell |
| Paper | [paper.md](paper.md) | Surface with background/shadow |
| Card | [card.md](card.md) | Structured surface with sections |
| Center | [center.md](center.md) | Center content |
| Space | [space.md](space.md) | Spacing element |
| Divider | [divider.md](divider.md) | Horizontal/vertical separator |
