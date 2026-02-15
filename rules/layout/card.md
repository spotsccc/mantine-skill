# Card

**Purpose:** Structured surface with full-bleed sections.

## Key props

Inherits all Paper props (`shadow`, `radius`, `withBorder`). Plus:
| Prop | Type | Description |
|------|------|--------------|
| `component` | React element type | Polymorphic — e.g. `component={Link}` for clickable cards |

**Card.Section:**
| Prop | Type | Description |
|------|------|--------------|
| `withBorder` | boolean | Bottom border |
| `inheritPadding` | boolean | Match card padding instead of full-bleed |

## Rules and gotchas

- Extends Paper — has all Paper styling.
- `Card.Section` takes full width of card (ignores parent padding) by default.
- Use `inheritPadding` on `Card.Section` to align content with card padding.
- Polymorphic — use `component={Link}` for clickable cards.

## Example

```tsx
<Card shadow="sm" radius="md" withBorder padding="lg">
  <Card.Section withBorder>
    <Image src="/hero.jpg" height={160} alt="" />
  </Card.Section>
  <Text fw={500} mt="sm">Title</Text>
  <Text size="sm" c="dimmed">Description</Text>
</Card>

<Card component={Link} to="/article/1" padding="md">
  Clickable card
</Card>
```
