# HoverCard

**Purpose:** Rich content popup shown on hover. User previews, quick info.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `openDelay` | number | Delay before open |
| `closeDelay` | number | Delay before close |
| `position` | PopoverPosition | Placement |
| `width` | number \| string | Dropdown width |
| `withinPortal` | boolean | Default true |
| `offset` | number | Distance from target |
| `withArrow` | boolean | Show arrow |

## Compound components

- **HoverCard.Target** — hover trigger (child must support ref)
- **HoverCard.Dropdown** — popup content

## Rules and gotchas

- **NOT accessible via keyboard** — use only as supplementary info
- **HoverCard.Target child must support ref**
- Dropdown stays open while hovered (target or dropdown)
- Combine with Popover if keyboard access needed

## Example

```tsx
<HoverCard width={280} openDelay={200} closeDelay={100}>
  <HoverCard.Target>
    <Avatar src={user.avatar} radius="xl" />
  </HoverCard.Target>
  <HoverCard.Dropdown>
    <Group>
      <Avatar src={user.avatar} size="lg" />
      <div>
        <Text fw={600}>{user.name}</Text>
        <Text size="xs" c="dimmed">@{user.login}</Text>
      </div>
    </Group>
  </HoverCard.Dropdown>
</HoverCard>
```
