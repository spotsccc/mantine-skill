# Code

**Purpose:** Inline and block code display.

## Key props

| Prop | Type | Description |
|------|------|-------------|
| `block` | boolean | Render as `<pre>` for multiline; default false = inline `<code>` |
| `color` | MantineColor | Background color (theme-aware) |

## Rules and gotchas

- Inline by default — renders `<code>` for snippets within text.
- `block={true}` — switches to `<pre>` for multiline code blocks.
- For syntax highlighting — use `@mantine/code-highlight` (CodeHighlight, Code) instead.

## Example

```tsx
<Text>Use <Code>npm install</Code> to install dependencies.</Text>

<Code block color="dark.6">
{`function greet() {
  return 'Hello, world!';
}`}
</Code>
```
