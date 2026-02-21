# Inputs & Buttons

## Decision tree

- **Text action** → [Button](button.md) (filled/outline/subtle/light/transparent/gradient variants)
- **Icon-only action** → [ActionIcon](action-icon.md) (MUST have `aria-label`)
- **Single line text** → [TextInput](text-input.md)
- **Multi-line text** → [Textarea](textarea.md) (autosize option)
- **Choose one from list** → [Select](select.md) (searchable option)
- **Choose many from list** → [MultiSelect](multi-select.md)
- **Free-form tags** → [TagsInput](tags-input.md) (allows arbitrary values)
- **Number entry** → [NumberInput](number-input.md) (min/max/step)
- **Password** → [PasswordInput](password-input.md) (visibility toggle)
- **Boolean toggle** → [Checkbox](checkbox.md) or [Switch](switch.md)
- **Single choice from group** → [Radio](radio.md) (Radio.Group required)
- **Range value** → [Slider](slider.md) (marks, RangeSlider for two thumbs)
- **File upload** → [FileInput](file-input.md) (accept, multiple)

## Common patterns

- All inputs share: `label`, `description`, `error`, `required`, `size`, `leftSection`, `rightSection`
- Use `error` prop for validation messages (shows red border + message below)
- Button `loading` state for async operations (disables pointer-events, shows Loader)
- ActionIcon **always** needs `aria-label` for accessibility

## Components

| Component | File | Purpose |
|-----------|------|---------|
| Button | [button.md](button.md) | Action trigger (button or link) |
| ActionIcon | [action-icon.md](action-icon.md) | Icon-only button |
| TextInput | [text-input.md](text-input.md) | Single-line text input |
| Textarea | [textarea.md](textarea.md) | Multi-line text input |
| Select | [select.md](select.md) | Single value from list |
| MultiSelect | [multi-select.md](multi-select.md) | Multiple values from list |
| TagsInput | [tags-input.md](tags-input.md) | Free-form tags with optional suggestions |
| NumberInput | [number-input.md](number-input.md) | Numeric input with increment/decrement |
| Checkbox | [checkbox.md](checkbox.md) | Boolean toggle (checkmark) |
| Switch | [switch.md](switch.md) | Boolean toggle (switch) |
| PasswordInput | [password-input.md](password-input.md) | Password with visibility toggle |
| Radio | [radio.md](radio.md) | Single selection from group |
| Slider | [slider.md](slider.md) | Value selection from range |
| FileInput | [file-input.md](file-input.md) | File selection input |
