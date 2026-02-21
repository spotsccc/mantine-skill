# Data Display

## Decision tree

| Need | Component |
|------|-----------|
| Tabular data | **Table** (Table.ScrollContainer for horizontal scroll) |
| Status label / tag | **Badge** |
| Picture | **Image** (with fallbackSrc) |
| User photo / initials | **Avatar** (Avatar.Group for stacking) |
| Icon with colored background | **ThemeIcon** |
| Chronological events | **Timeline** |
| Notification dot / count | **Indicator** |
| Bulleted / numbered items | **List** |
| Collapsible sections | **Accordion** |

## Common patterns

- **Table** compound components: `Table.Thead`, `Table.Tbody`, `Table.Tr`, `Table.Th`, `Table.Td`
- **Badge** `variant` controls appearance: filled, light, outline, dot, gradient
- **Image**: always set `alt` for accessibility
- **Avatar.Group**: children must be direct Avatar elements (no wrappers)

## Components

| Component | File | Purpose |
|-----------|------|---------|
| Table | [table.md](table.md) | Themed HTML table |
| Badge | [badge.md](badge.md) | Status label, tag, count |
| Image | [image.md](image.md) | Image with optional fallback |
| Avatar | [avatar.md](avatar.md) | User photo / initials |
| ThemeIcon | [theme-icon.md](theme-icon.md) | Icon with colored background |
| Timeline | [timeline.md](timeline.md) | Chronological events |
| Indicator | [indicator.md](indicator.md) | Notification dot / count on element |
| List | [list.md](list.md) | Styled ordered / unordered list |
| Accordion | [accordion.md](accordion.md) | Collapsible sections |
