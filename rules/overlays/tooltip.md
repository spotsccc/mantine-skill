# Tooltip

**Purpose:** Simple text hint shown on hover/focus. Icon explanations, shortcuts.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `label` | ReactNode | **Required.** Hint text |
| `position` | TooltipPosition | Placement |
| `offset` | number | Distance from target |
| `withArrow` | boolean | Show arrow |
| `arrowSize` | number | Arrow dimensions |
| `multiline` | boolean | Wrap long text |
| `w` | number | Width for multiline |
| `color` | MantineColor | Tooltip color |
| `openDelay` / `closeDelay` | number | Timing |
| `events` | object | `{ hover, focus, touch }` |
| `inline` | boolean | For inline elements (span) |
| `disabled` | boolean | Disable tooltip |

## Rules and gotchas

- **Child MUST be single element that accepts ref** — NOT string, NOT fragment
- Disabled buttons: use `data-disabled` instead of `disabled` (otherwise `onMouseLeave` won't fire)
- `inline` for inline elements (span)
- `Tooltip.Floating` follows cursor
- `Tooltip.Group` shares open delay across multiple tooltips
- `multiline` + `w={200}` for long text

## Example

```tsx
<Tooltip label="Save" withArrow>
  <ActionIcon>
    <IconDeviceFloppy />
  </ActionIcon>
</Tooltip>

<Tooltip label="Long tooltip text for a complex action" multiline w={200}>
  <Button>Details</Button>
</Tooltip>
```
