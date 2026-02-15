# Tabs

**Purpose:** Content tab switching (horizontal or vertical).

## Key props (Tabs)

| Prop | Type | Description |
|------|------|-------------|
| `value` / `defaultValue` | string | Active tab id |
| `onChange` | (value) => void | Switch handler |
| `orientation` | `"horizontal"` \| `"vertical"` | Layout |
| `variant` | `"default"` \| `"outline"` \| `"pills"` | Visual style |
| `color` | MantineColor | Indicator color |
| `keepMounted` | boolean | Default true — panels stay in DOM |
| `allowTabDeactivation` | boolean | Allow deselecting all tabs |

## Compound structure

- **Tabs.List** — container for tabs
- **Tabs.Tab** — tab button (`value` must match panel)
- **Tabs.Panel** — content panel (`value` must match tab)

## Rules and gotchas

- `value` on Tabs.Tab and Tabs.Panel must match
- `keepMounted=true` keeps unmounted panels in DOM (good for forms)
- `orientation="vertical"` needs explicit layout (flex direction)
- Tabs.Tab supports `leftSection`, `rightSection`, `color`
- Controlled: `value` + `onChange`

## Example

```tsx
<Tabs defaultValue="general" onChange={setActive}>
  <Tabs.List>
    <Tabs.Tab value="general">General</Tabs.Tab>
    <Tabs.Tab value="security">Security</Tabs.Tab>
  </Tabs.List>
  <Tabs.Panel value="general">General settings</Tabs.Panel>
  <Tabs.Panel value="security">Security settings</Tabs.Panel>
</Tabs>
```
