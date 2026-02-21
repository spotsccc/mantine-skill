# Sections

This file defines all sections, their ordering, and descriptions.
The section ID (in parentheses) is the subdirectory name inside `rules/`.

---

## 1. Best Practices (best-practices)

**Scope:** Styling, theming, responsive design, CSS variables, performance
**Description:** Fundamental styling rules and patterns that apply across all Mantine components. Covers styling priority, Styles API, responsive design, PostCSS preset, and polymorphic components.

## 2. Layout (layout)

**Scope:** Container, Grid, SimpleGrid, Stack, Group, Flex, Box, AppShell, Paper, Card, Center, Space, Divider
**Description:** Page structure and content arrangement. Decision trees for choosing between Stack/Group/Flex and Grid/SimpleGrid, plus page-level layout with AppShell.

## 3. Typography (typography)

**Scope:** Text, Title, Anchor, Code, Highlight, TypographyStylesProvider
**Description:** Text rendering, headings, links, code display, and raw HTML styling with theme integration.

## 4. Inputs & Buttons (inputs)

**Scope:** Button, ActionIcon, TextInput, Textarea, Select, MultiSelect, TagsInput, NumberInput, Checkbox, Switch
**Description:** Form controls and action triggers. Covers accessibility requirements (aria-label for ActionIcon), polymorphic navigation buttons, and selection component differences.

## 5. Data Display (data-display)

**Scope:** Table, Badge, Image, Avatar, ThemeIcon, Timeline, Indicator, List, Accordion
**Description:** Structured data presentation. Tables with sticky headers and scroll containers, status indicators, collapsible content, and image handling.

## 6. Navigation (navigation)

**Scope:** NavLink, Breadcrumbs, Burger, Menu, Tabs, Pagination, Stepper
**Description:** Navigation patterns from sidebar links to multi-step wizards. Compound component structures for Menu and Tabs, accessibility for Burger toggle.

## 7. Feedback (feedback)

**Scope:** Alert, Notification, Loader, LoadingOverlay, Skeleton, Progress
**Description:** User feedback and loading states. Toast notification system via `@mantine/notifications`, overlay patterns, and content placeholders.

## 8. Overlays (overlays)

**Scope:** Modal, Drawer, Popover, Tooltip, HoverCard
**Description:** Overlay dialogs, side panels, and positioned popups. Focus management, portal rendering, and useDisclosure integration.

## 9. Hooks (hooks)

**Scope:** useDisclosure, useDebouncedValue, useMediaQuery, useClickOutside, useIntersection, useHotkeys
**Description:** Utility hooks from `@mantine/hooks`. Boolean state management, debouncing, media queries (SSR caveats), click outside detection, intersection observation, and keyboard shortcuts.
