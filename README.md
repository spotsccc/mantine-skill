# Mantine Skill for AI Agents

An AI agent skill that provides comprehensive rules, best practices, and component-specific guidance for building UIs with **Mantine v8**.

## What's Inside

- **SKILL.md** — entry point with general rules, theme tokens, styling priority, and category index
- **best-practices.md** — styling priority guide (props → Style props → CSS Modules → `style`)
- **8 component categories**, each with a README and per-component files:

| Category | Components |
|----------|------------|
| **Layout** | Container, Grid, SimpleGrid, Stack, Group, Flex, Box, AppShell, Paper, Card, Center, Space, Divider |
| **Typography** | Text, Title, Anchor, Code, Highlight, TypographyStylesProvider |
| **Inputs & Buttons** | Button, ActionIcon, TextInput, Textarea, Select, MultiSelect, TagsInput, NumberInput, Checkbox, Switch |
| **Data Display** | Table, Badge, Image, Avatar, ThemeIcon, Timeline, Indicator, List, Accordion |
| **Navigation** | NavLink, Breadcrumbs, Burger, Menu, Tabs, Pagination, Stepper |
| **Feedback** | Alert, Notification, Loader, LoadingOverlay, Skeleton, Progress |
| **Overlays** | Modal, Drawer, Popover, Tooltip, HoverCard |
| **Hooks** | useDisclosure, useDebouncedValue, useMediaQuery, useClickOutside, useIntersection, useHotkeys |

## Installation

### Cursor

Clone (or add as a submodule) into your skills directory:

```bash
git clone https://github.com/spotsccc/mantine-skill.git ~/.cursor/skills/mantine
```

The skill will be automatically picked up when the agent detects Mantine-related code.

### Codex

```bash
git clone https://github.com/spotsccc/mantine-skill.git ~/.codex/skills/mantine
```

## Usage

The agent reads `SKILL.md` as the entry point. From there it navigates to the relevant category README and then to component-specific files as needed. No manual intervention required — just work with Mantine components and the agent will reference the right guidelines.

## License

[MIT](LICENSE)
