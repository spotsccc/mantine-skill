---
name: mantine-ui
description: Rules and best practices for Mantine v8 UI library. Use when working with @mantine/core, @mantine/hooks, @mantine/notifications components, or when building UI with Mantine. Covers styling, theming, responsive design, and component-specific patterns.
user-invocable: false
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

## Quick Reference

### 1. Best Practices

- [best-practices](rules/best-practices.md) — Styling priority, Styles API, responsive design, PostCSS, polymorphic components, CSS variables

### 2. Layout

Read decision tree: [rules/layout/README.md](rules/layout/README.md)

- [layout/container](rules/layout/container.md) — Max-width centered wrapper
- [layout/grid](rules/layout/grid.md) — 12-column responsive grid
- [layout/simple-grid](rules/layout/simple-grid.md) — Equal-width responsive grid
- [layout/stack](rules/layout/stack.md) — Vertical flex container
- [layout/group](rules/layout/group.md) — Horizontal flex container
- [layout/flex](rules/layout/flex.md) — Full-control flex container
- [layout/box](rules/layout/box.md) — Generic wrapper (div)
- [layout/app-shell](rules/layout/app-shell.md) — Page-level layout shell
- [layout/paper](rules/layout/paper.md) — Surface with background/shadow
- [layout/card](rules/layout/card.md) — Structured surface with sections
- [layout/center](rules/layout/center.md) — Center content
- [layout/space](rules/layout/space.md) — Spacing element
- [layout/divider](rules/layout/divider.md) — Horizontal/vertical separator

### 3. Typography

Read decision tree: [rules/typography/README.md](rules/typography/README.md)

- [typography/text](rules/typography/text.md) — Display text with theme styles
- [typography/title](rules/typography/title.md) — Semantic headings h1–h6
- [typography/anchor](rules/typography/anchor.md) — Themed link element
- [typography/code](rules/typography/code.md) — Inline and block code
- [typography/highlight](rules/typography/highlight.md) — Highlight matching substrings
- [typography/typography-styles-provider](rules/typography/typography-styles-provider.md) — Apply theme to raw HTML

### 4. Inputs & Buttons

Read decision tree: [rules/inputs/README.md](rules/inputs/README.md)

- [inputs/button](rules/inputs/button.md) — Action trigger (button or link)
- [inputs/action-icon](rules/inputs/action-icon.md) — Icon-only button
- [inputs/text-input](rules/inputs/text-input.md) — Single-line text input
- [inputs/textarea](rules/inputs/textarea.md) — Multi-line text input
- [inputs/select](rules/inputs/select.md) — Single value from list
- [inputs/multi-select](rules/inputs/multi-select.md) — Multiple values from list
- [inputs/tags-input](rules/inputs/tags-input.md) — Free-form tags with suggestions
- [inputs/number-input](rules/inputs/number-input.md) — Numeric input with increment/decrement
- [inputs/checkbox](rules/inputs/checkbox.md) — Boolean toggle (checkmark)
- [inputs/switch](rules/inputs/switch.md) — Boolean toggle (switch)

### 5. Data Display

Read decision tree: [rules/data-display/README.md](rules/data-display/README.md)

- [data-display/table](rules/data-display/table.md) — Themed HTML table
- [data-display/badge](rules/data-display/badge.md) — Status label, tag, count
- [data-display/image](rules/data-display/image.md) — Image with optional fallback
- [data-display/avatar](rules/data-display/avatar.md) — User photo / initials
- [data-display/theme-icon](rules/data-display/theme-icon.md) — Icon with colored background
- [data-display/timeline](rules/data-display/timeline.md) — Chronological events
- [data-display/indicator](rules/data-display/indicator.md) — Notification dot / count on element
- [data-display/list](rules/data-display/list.md) — Styled ordered / unordered list
- [data-display/accordion](rules/data-display/accordion.md) — Collapsible sections

### 6. Navigation

Read decision tree: [rules/navigation/README.md](rules/navigation/README.md)

- [navigation/nav-link](rules/navigation/nav-link.md) — Sidebar link with icon, description
- [navigation/breadcrumbs](rules/navigation/breadcrumbs.md) — Path navigation breadcrumbs
- [navigation/burger](rules/navigation/burger.md) — Mobile menu toggle
- [navigation/menu](rules/navigation/menu.md) — Dropdown action menu
- [navigation/tabs](rules/navigation/tabs.md) — Content tab switching
- [navigation/pagination](rules/navigation/pagination.md) — Page number navigation
- [navigation/stepper](rules/navigation/stepper.md) — Multi-step wizard / progress

### 7. Feedback

Read decision tree: [rules/feedback/README.md](rules/feedback/README.md)

- [feedback/alert](rules/feedback/alert.md) — Static important message block
- [feedback/notification](rules/feedback/notification.md) — Toast notification
- [feedback/loader](rules/feedback/loader.md) — Spinning indicator
- [feedback/loading-overlay](rules/feedback/loading-overlay.md) — Block UI during loading
- [feedback/skeleton](rules/feedback/skeleton.md) — Content placeholder
- [feedback/progress](rules/feedback/progress.md) — Progress bar

### 8. Overlays

Read decision tree: [rules/overlays/README.md](rules/overlays/README.md)

- [overlays/modal](rules/overlays/modal.md) — Accessible overlay dialog
- [overlays/drawer](rules/overlays/drawer.md) — Side panel overlay
- [overlays/popover](rules/overlays/popover.md) — Anchored popup with rich content
- [overlays/tooltip](rules/overlays/tooltip.md) — Simple text hint on hover
- [overlays/hover-card](rules/overlays/hover-card.md) — Rich content preview on hover

### 9. Hooks

Read decision tree: [rules/hooks/README.md](rules/hooks/README.md)

- [hooks/use-disclosure](rules/hooks/use-disclosure.md) — Boolean state (open/close/toggle)
- [hooks/use-debounced-value](rules/hooks/use-debounced-value.md) — Debounce input value
- [hooks/use-media-query](rules/hooks/use-media-query.md) — Viewport width (NOT SSR-safe)
- [hooks/use-click-outside](rules/hooks/use-click-outside.md) — Detect click outside element
- [hooks/use-intersection](rules/hooks/use-intersection.md) — Observe element visibility
- [hooks/use-hotkeys](rules/hooks/use-hotkeys.md) — Keyboard shortcuts

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
