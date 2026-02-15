# TextInput

**Purpose:** Single-line text input.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `label` | ReactNode | Label above input |
| `description` | ReactNode | Helper text below label |
| `error` | ReactNode | Validation message (red border + text) |
| `required` | boolean | Asterisk + native required |
| `placeholder` | string | Placeholder text |
| `size` | MantineSize | Input height |
| `radius` | MantineRadius | Corner radius |
| `leftSection` / `rightSection` | ReactNode | Icon or content |
| `leftSectionWidth` / `rightSectionWidth` | number | Override auto width |
| `disabled` | boolean | Disabled state |
| `withErrorStyles` | boolean | Default true; show red border on error |

## Rules and gotchas

- **Label required for a11y** — always use `label` (or `aria-label` if label hidden).
- `error` shows error message under input and red border (unless `withErrorStyles={false}`).
- Section widths adjust automatically; override with `leftSectionWidth` / `rightSectionWidth` for custom icons.

## Example

```tsx
<TextInput
  label="Email"
  placeholder="user@example.com"
  error={errors.email?.message}
  required
  leftSection={<IconMail size={16} />}
/>
```
