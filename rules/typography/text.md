# Text

**Purpose:** Display text with theme styles.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `size` | `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` | Font size preset |
| `c` | MantineColor | Color (use `"dimmed"` for secondary text) |
| `fw` | number | Font weight |
| `ta` | `"left"` \| `"center"` \| `"right"` | Text alignment |
| `td` | `"none"` \| `"underline"` \| `"line-through"` | Text decoration |
| `tt` | `"none"` \| `"uppercase"` \| `"lowercase"` \| `"capitalize"` | Text transform |
| `truncate` | `true` \| `"start"` \| `"end"` | Ellipsis truncation |
| `lineClamp` | number | Max visible lines (clips with ellipsis) |
| `span` | boolean | Render `<span>` instead of `<p>` |
| `inherit` | boolean | Inherit parent font styles |
| `gradient` | MantineGradient | With `variant="gradient"` for gradient text |
| `variant` | `"text"` \| `"gradient"` | Gradient requires `variant="gradient"` |

## Rules and gotchas

- Default renders `<p>` — use `span` prop (not `component="span"`) for inline text.
- `c="dimmed"` — standard pattern for secondary/muted text.
- `truncate` — adds ellipsis; use `"start"` or `"end"` for directional truncation.
- `lineClamp` — do NOT add padding-bottom; it can cause layout issues.
- `inherit` — makes Text inherit parent `font-size`, `line-height`, `color`.
- Polymorphic — supports `component` for custom root element.

## Example

```tsx
<Text size="sm" c="dimmed">Secondary caption</Text>

<Text truncate maw={200}>Long text that will be truncated...</Text>

<Text lineClamp={3}>Multi-line text limited to 3 lines...</Text>

<Text span inherit>Inline text inheriting parent styles</Text>

<Text variant="gradient" gradient={{ from: 'blue', to: 'cyan', deg: 45 }}>Gradient text</Text>
```
