---
description: Mantine Accordion — collapsible content sections. Compound: Accordion.Item, Accordion.Control, Accordion.Panel.
---

# Accordion

## Purpose

Collapsible content sections. Controlled or uncontrolled.

## Key props

| Prop | Type | Notes |
|------|------|-------|
| `value` \| `defaultValue` | string \| string[] | Active item(s) |
| `onChange` | handler | For controlled mode |
| `multiple` | boolean | Allow multiple open items |
| `chevron` | ReactNode \| null | Custom chevron or none |
| `chevronPosition` | "left" \| "right" | Chevron side |
| `transitionDuration` | number | Open/close animation |
| `order` | 2-6 | Heading level (h2-h6) for a11y |
| `radius` | "xs"\..."xl" | Item corner radius |
| `loop` | boolean | Focus trap in open item |

## Compound components

`Accordion.Item` (requires `value`), `Accordion.Control`, `Accordion.Panel`

## Rules

- **Do NOT** put interactive elements (buttons, links) inside Accordion.Control; use only text or passive content.
- With `multiple={false}`: `value` is `string | null`.
- With `multiple={true}`: `value` is `string[]`.
- `order` sets heading level for accessibility (default h3).
- Set `chevron={null}` to remove chevron, or pass custom ReactNode.

## Example

```tsx
<Accordion
  value={openId}
  onChange={setOpenId}
  multiple={false}
  chevronPosition="right"
>
  <Accordion.Item value="faq-1">
    <Accordion.Control>How do I start?</Accordion.Control>
    <Accordion.Panel>Follow the setup guide...</Accordion.Panel>
  </Accordion.Item>
  <Accordion.Item value="faq-2">
    <Accordion.Control>Pricing</Accordion.Control>
    <Accordion.Panel>See our plans...</Accordion.Panel>
  </Accordion.Item>
</Accordion>
```
