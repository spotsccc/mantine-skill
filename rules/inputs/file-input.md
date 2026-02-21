# FileInput

**Purpose:** File selection input (styled like TextInput).

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `accept` | string | Accepted MIME types (e.g. `"image/*"`, `"application/pdf"`) |
| `multiple` | boolean | Allow selecting multiple files |
| `clearable` | boolean | Show clear button when file is selected |
| `valueComponent` | `FC<{ value: File \| File[] }>` | Custom display for selected file(s) |
| `capture` | `"user"` \| `"environment"` | Mobile camera capture mode |
| `value` | `File \| File[] \| null` | Controlled value |
| `onChange` | `(value: File \| File[] \| null) => void` | Called when files change |
| `label` | ReactNode | Label above input |
| `description` | ReactNode | Helper text below label |
| `error` | ReactNode | Validation message |

## Rules and gotchas

- **`value`** is `File | null` (single) or `File[] | null` (when `multiple`), not a string path.
- **`accept`** takes MIME type strings (e.g. `"image/*"`, `"image/png,image/jpeg"`, `".pdf"`).
- **`clearable`** adds an X button to remove the selected file — recommended for optional fields.
- **`valueComponent`** lets you customize how selected files are rendered (e.g. show file size, icon).
- Shares all standard input props (`label`, `description`, `error`, `required`, `size`, etc.) with TextInput.

## Example

```tsx
<FileInput
  label="Upload document"
  placeholder="Click to select file"
  accept="application/pdf,image/*"
  clearable
  value={file}
  onChange={setFile}
/>

{/* Multiple files */}
<FileInput
  label="Attachments"
  multiple
  accept="image/*"
  value={files}
  onChange={setFiles}
/>
```
