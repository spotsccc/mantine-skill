# Mantine Skill for AI Agents

An AI agent skill that provides comprehensive rules, best practices, and component-specific guidance for building UIs with **Mantine v8**.

## Structure

```
SKILL.md                           # Entry point — categories, quick reference, theme tokens
rules/
  _sections.md                     # Section definitions and descriptions
  _template.md                     # Template for new component rules
  best-practices.md                # Styling priority, Styles API, responsive, CSS variables
  layout/
    README.md                      # Decision tree: Stack vs Group vs Flex, Grid vs SimpleGrid
    container.md, grid.md, simple-grid.md, stack.md, group.md, flex.md,
    box.md, app-shell.md, paper.md, card.md, center.md, space.md, divider.md
  typography/
    README.md                      # Decision tree for text components
    text.md, title.md, anchor.md, code.md, highlight.md, typography-styles-provider.md
  inputs/
    README.md                      # Decision tree for inputs and buttons
    button.md, action-icon.md, text-input.md, textarea.md, select.md,
    multi-select.md, tags-input.md, number-input.md, checkbox.md, switch.md
  data-display/
    README.md                      # Decision tree for data display
    table.md, badge.md, image.md, avatar.md, theme-icon.md, timeline.md,
    indicator.md, list.md, accordion.md
  navigation/
    README.md                      # Decision tree for navigation
    nav-link.md, breadcrumbs.md, burger.md, menu.md, tabs.md, pagination.md, stepper.md
  feedback/
    README.md                      # Decision tree for feedback
    alert.md, notification.md, loader.md, loading-overlay.md, skeleton.md, progress.md
  overlays/
    README.md                      # Decision tree for overlays
    modal.md, drawer.md, popover.md, tooltip.md, hover-card.md
  hooks/
    README.md                      # Decision tree for hooks
    use-disclosure.md, use-debounced-value.md, use-media-query.md,
    use-click-outside.md, use-intersection.md, use-hotkeys.md
```

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

The agent reads `SKILL.md` as the entry point. From there it navigates to the relevant category `README.md` (decision tree) and then to component-specific rule files as needed.

Each category directory contains:
- **README.md** — decision tree for choosing the right component, comparison tables, common patterns
- **Component files** — key props, rules/gotchas, and code examples

## Versioning

This skill targets **Mantine v8**. The skill version in `SKILL.md` frontmatter (`metadata.version`) tracks the skill's own evolution, not the Mantine version.

When a new major Mantine version is released (e.g. v9):
- A new branch (e.g. `mantine-v9`) will be created for the updated skill
- The `main` branch will continue to track the latest stable Mantine version
- Breaking API changes in Mantine will be reflected in updated component files

To pin to a specific Mantine version, use a tagged release or branch.

## License

[MIT](LICENSE)
