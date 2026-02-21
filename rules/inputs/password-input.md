# PasswordInput

**Purpose:** Password input with visibility toggle.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `visible` | boolean | Controlled visibility state |
| `onVisibilityChange` | `(visible: boolean) => void` | Called when toggle is clicked |
| `visibilityToggleIcon` | `(props: { reveal: boolean }) => ReactNode` | Custom toggle icon |
| `visibilityToggleButtonProps` | Record\<string, any\> | Props for the toggle button |
| `label` | ReactNode | Label above input |
| `description` | ReactNode | Helper text below label |
| `error` | ReactNode | Validation message (red border + text) |
| `size` | MantineSize | Input height |
| `leftSection` | ReactNode | Icon or content on the left |

## Rules and gotchas

- **Controlled visibility:** use `visible` + `onVisibilityChange` to control reveal state externally.
- **Toggle button a11y:** `visibilityToggleButtonProps` lets you set `aria-label` on the toggle (defaults are provided).
- **Forms:** use `autoComplete="current-password"` for login forms and `autoComplete="new-password"` for registration.
- Shares all standard input props (`label`, `description`, `error`, `required`, `leftSection`, etc.) with TextInput.

## Example

```tsx
<PasswordInput
  label="Password"
  placeholder="Enter password"
  error={errors.password?.message}
  required
  autoComplete="current-password"
/>

{/* Controlled visibility */}
<PasswordInput
  label="Password"
  visible={visible}
  onVisibilityChange={setVisible}
/>
```
