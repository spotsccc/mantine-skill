---
name: mantine-ui
description: Rules and best practices for Mantine v8 UI library. Use when working with @mantine/core, @mantine/hooks, @mantine/notifications components, or when building UI with Mantine. Covers styling, theming, responsive design, and component-specific patterns.
license: MIT
metadata:
  author: spotsccc
  version: "1.0.0"
---

# Mantine v8 UI Library

Comprehensive component and styling guide for Mantine v8, designed for AI agents and LLMs. Contains rules across 9 categories covering 50+ components and hooks, with decision trees, props reference, gotchas, and code examples.

## When to Apply

Reference these guidelines when:
- Building UI with `@mantine/core` components
- Using `@mantine/hooks` in React components
- Implementing toast notifications with `@mantine/notifications`
- Styling Mantine components (choosing between props, CSS Modules, Styles API)
- Setting up theming with `createTheme()` and `MantineProvider`
- Working with Next.js + Mantine integration

## General

- Version: **Mantine v8** (`@mantine/core`, `@mantine/hooks`, `@mantine/notifications`)
- All components: `import { Component } from '@mantine/core'`
- Hooks: `import { useHook } from '@mantine/hooks'`
- Notifications: `import { notifications } from '@mantine/notifications'`
- Theme: `createTheme()` + `MantineProvider`; access via `useMantineTheme()`

## All components support

- `className`, `classNames` (Styles API), `style`, `styles`
- Style props: `m`, `p`, `c`, `bg`, `fz`, `fw`, `ta`, `w`, `h`, `maw`, `mah`, `pos`, etc.
- Responsive: `hiddenFrom`, `visibleFrom` (breakpoint-based show/hide)
- Polymorphic: `component` prop to change root element

## Rule Categories

| # | Category | Prefix | Components / Scope |
|---|----------|--------|--------------------|
| 1 | Best Practices | `best-practices` | Styling, theming, responsive, CSS variables |
| 2 | Layout | `layout/` | Container, Grid, SimpleGrid, Stack, Group, Flex, Box, AppShell, Paper, Card, Center, Space, Divider |
| 3 | Typography | `typography/` | Text, Title, Anchor, Code, Highlight, TypographyStylesProvider |
| 4 | Inputs & Buttons | `inputs/` | Button, ActionIcon, TextInput, Textarea, Select, MultiSelect, TagsInput, NumberInput, Checkbox, Switch |
| 5 | Data Display | `data-display/` | Table, Badge, Image, Avatar, ThemeIcon, Timeline, Indicator, List, Accordion |
| 6 | Navigation | `navigation/` | NavLink, Breadcrumbs, Burger, Menu, Tabs, Pagination, Stepper |
| 7 | Feedback | `feedback/` | Alert, Notification, Loader, LoadingOverlay, Skeleton, Progress |
| 8 | Overlays | `overlays/` | Modal, Drawer, Popover, Tooltip, HoverCard |
| 9 | Hooks | `hooks/` | useDisclosure, useDebouncedValue, useMediaQuery, useClickOutside, useIntersection, useHotkeys |

## Navigation

To find the right component, read the decision tree in the relevant category:

- [rules/best-practices.md](rules/best-practices.md) — Styling priority, Styles API, responsive design, CSS variables
- [rules/layout/README.md](rules/layout/README.md) — Layout decision tree
- [rules/typography/README.md](rules/typography/README.md) — Typography decision tree
- [rules/inputs/README.md](rules/inputs/README.md) — Inputs & Buttons decision tree
- [rules/data-display/README.md](rules/data-display/README.md) — Data Display decision tree
- [rules/navigation/README.md](rules/navigation/README.md) — Navigation decision tree
- [rules/feedback/README.md](rules/feedback/README.md) — Feedback decision tree
- [rules/overlays/README.md](rules/overlays/README.md) — Overlays decision tree
- [rules/hooks/README.md](rules/hooks/README.md) — Hooks decision tree

Each category `README.md` contains a decision tree and links to individual component files with props, gotchas, and examples.

## Theme Tokens (CSS Variables)

| Token | CSS Variable | Style prop |
|-------|-------------|------------|
| Spacing | `var(--mantine-spacing-{xs\|sm\|md\|lg\|xl})` | `p`, `m`, `gap` |
| Colors | `var(--mantine-color-{name}-{0-9})` | `c`, `bg` (`"blue.6"`) |
| Font size | `var(--mantine-font-size-{size})` | `fz` |
| Radius | `var(--mantine-radius-{size})` | `radius` prop |
| Shadow | `var(--mantine-shadow-{size})` | `shadow` prop |
| Headings | `var(--mantine-h{1-6}-font-size)` | Title `order` |
| Primary | `var(--mantine-primary-color-filled)` | `color` prop |

## Next.js Pages Router

- `ColorSchemeScript` in `_document.tsx`, `mantineHtmlProps` on `<Html>`
- `MantineProvider` in `_app.tsx`
- `@mantine/*` packages in `transpilePackages` (next.config)
- Use `component={Link}` for Next.js Link (v13+)
- All Mantine components are client components (`'use client'` already in entry points)

## How to Use

Read individual rule files for detailed props, gotchas, and code examples:

```
rules/best-practices.md
rules/layout/container.md
rules/inputs/select.md
rules/hooks/use-disclosure.md
```

Each category directory contains:
- `README.md` — decision tree for choosing the right component, comparison tables, common patterns
- Component files — key props, rules/gotchas, and code examples

Styling priority: **Component props > Style props > CSS Modules > style prop**. Read [rules/best-practices.md](rules/best-practices.md) first.
