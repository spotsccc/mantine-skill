---
name: mantine-ui
description: Rules and best practices for Mantine v8 UI library. Use when working with @mantine/core, @mantine/hooks, @mantine/notifications components, or when building UI with Mantine. Covers styling, theming, responsive design, and component-specific patterns.
---

# Mantine v8 UI Library

## General

- Version: **Mantine v8** (`@mantine/core`, `@mantine/hooks`, `@mantine/notifications`)
- All components: `import { Component } from '@mantine/core'`
- Hooks: `import { useHook } from '@mantine/hooks'`
- Notifications: `import { notifications } from '@mantine/notifications'`
- Theme: `createTheme()` + `MantineProvider`; access via `useMantineTheme()`

## Styling priority

Before writing any styles, read [best-practices.md](best-practices.md).

Quick rule: **Component props > Style props > CSS Modules > style prop**. Avoid `style={{...}}` when a Mantine prop exists.

## All components support

- `className`, `classNames` (Styles API), `style`, `styles`
- Style props: `m`, `p`, `c`, `bg`, `fz`, `fw`, `ta`, `w`, `h`, `maw`, `mah`, `pos`, etc.
- Responsive: `hiddenFrom`, `visibleFrom` (breakpoint-based show/hide)
- Polymorphic: `component` prop to change root element

## Categories

Pick the category for the component you need, then read its README for decision trees and component-specific files.

| Category | Path | Components |
|----------|------|------------|
| Layout | [layout/README.md](layout/README.md) | Container, Grid, SimpleGrid, Stack, Group, Flex, Box, AppShell, Paper, Card, Center, Space, Divider |
| Typography | [typography/README.md](typography/README.md) | Text, Title, Anchor, Code, Highlight, TypographyStylesProvider |
| Inputs & Buttons | [inputs/README.md](inputs/README.md) | Button, ActionIcon, TextInput, Textarea, Select, MultiSelect, TagsInput, NumberInput, Checkbox, Switch |
| Data Display | [data-display/README.md](data-display/README.md) | Table, Badge, Image, Avatar, ThemeIcon, Timeline, Indicator, List, Accordion |
| Navigation | [navigation/README.md](navigation/README.md) | NavLink, Breadcrumbs, Burger, Menu, Tabs, Pagination, Stepper |
| Feedback | [feedback/README.md](feedback/README.md) | Alert, Notification, Loader, LoadingOverlay, Skeleton, Progress |
| Overlays | [overlays/README.md](overlays/README.md) | Modal, Drawer, Popover, Tooltip, HoverCard |
| Hooks | [hooks/README.md](hooks/README.md) | useDisclosure, useDebouncedValue, useMediaQuery, useClickOutside, useIntersection, useHotkeys |

## Theme tokens (CSS variables)

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
