# Timeline

**Purpose:** Chronological event list. Highlights items up to the active step.

## Key props (Timeline)

| Prop | Type | Description |
|------|------|-------------|
| `active` | number | Index of current step (highlights 0..active) |
| `color` | string | Line and bullet color |
| `lineWidth` | number | Connector line width |
| `bulletSize` | number | Default bullet size |
| `align` | "left" \| "right" | Layout direction |

## Key props (Timeline.Item)

| Prop | Type | Description |
|------|------|-------------|
| `title` | ReactNode | Item title |
| `bullet` | ReactNode | Custom marker (Icon, Avatar, ThemeIcon) |
| `lineVariant` | "solid" \| "dashed" \| "dotted" | Connector style |

## Rules and gotchas

- Children must be direct **Timeline.Item** elements.
- `active` highlights items from index 0 up to (and including) that index.
- Custom bullets via `bullet` prop: pass Icon, Avatar, ThemeIcon, etc.

## Example

```tsx
<Timeline active={1} color="blue" bulletSize={24}>
  <Timeline.Item title="Order placed" bullet={<IconCheck size={12} />} />
  <Timeline.Item title="Shipped" bullet={<IconTruck size={12} />} />
  <Timeline.Item title="Delivered" />
</Timeline>
```
