---
description: Mantine Table — themed HTML table with sticky header, stripes, borders. Use Table.ScrollContainer for horizontal scroll.
---

# Table

## Purpose

Themed HTML table for tabular data. Supports sticky headers, stripes, borders, responsive scroll.

## Key props

| Prop | Type | Notes |
|------|------|-------|
| `data` | `{ head, body, foot, caption }` | Shorthand: use OR compound components |
| `stickyHeader` | boolean | Fix thead on scroll |
| `stickyHeaderOffset` | number | Offset when fixed header above (e.g. AppShell) |
| `highlightOnHover` | boolean | Row hover highlight |
| `striped` | true \| "odd" \| "even" | Striped rows |
| `horizontalSpacing` | "xs"\..."xl" | Cell padding |
| `verticalSpacing` | "xs"\..."xl" | Row padding |
| `withTableBorder` | boolean | Table outer border |
| `withColumnBorders` | boolean | Vertical borders |
| `withRowBorders` | boolean | Horizontal borders |
| `tabularNums` | boolean | Align numbers by digit |
| `captionSide` | "top" \| "bottom" | Caption position |

## Compound components

`Table.Thead`, `Table.Tbody`, `Table.Tfoot`, `Table.Tr`, `Table.Th`, `Table.Td`, `Table.Caption`, `Table.ScrollContainer`

## Rules

- Use `data` prop **OR** compound components — not both.
- **Table.ScrollContainer** with `minWidth` for responsive horizontal scroll; `type="native"` for native scrollbar.
- When using `stickyHeader`, set `stickyHeaderOffset` if there is a fixed header above (e.g. AppShell navbar).
- Use `tabularNums` for aligned numeric columns.

## Example

```tsx
<Table.ScrollContainer minWidth={600} type="native">
  <Table highlightOnHover striped withTableBorder>
    <Table.Thead>
      <Table.Tr>
        <Table.Th>Name</Table.Th>
        <Table.Th ta="right" style={{ fontVariantNumeric: 'tabular-nums' }}>Amount</Table.Th>
      </Table.Tr>
    </Table.Thead>
    <Table.Tbody>
      {rows.map((row) => (
        <Table.Tr key={row.id}>
          <Table.Td>{row.name}</Table.Td>
          <Table.Td ta="right">{row.amount}</Table.Td>
        </Table.Tr>
      ))}
    </Table.Tbody>
  </Table>
</Table.ScrollContainer>
```
