---
description: Feedback components — alerts, notifications, loaders, skeletons, progress. Use for user feedback, loading states, and status indicators.
---

# Feedback

## Decision tree

| Need | Component |
|------|-----------|
| Static important message | **Alert** |
| Toast notification | **Notification** (via @mantine/notifications) |
| Spinning indicator | **Loader** |
| Block UI during loading | **LoadingOverlay** (needs parent with `pos="relative"`) |
| Content placeholder | **Skeleton** |
| Progress bar | **Progress** |

## Common patterns

- For toast notifications use `notifications.show()` from `@mantine/notifications` (NOT the Notification component directly)
- LoadingOverlay parent needs `position: relative`
- Skeleton matches dimensions of content it replaces

## Components

| Component | File | Purpose |
|-----------|------|---------|
| Alert | [alert.md](alert.md) | Static important message block |
| Notification | [notification.md](notification.md) | Toast notification |
| Loader | [loader.md](loader.md) | Spinning indicator |
| LoadingOverlay | [loading-overlay.md](loading-overlay.md) | Block UI during loading |
| Skeleton | [skeleton.md](skeleton.md) | Content placeholder |
| Progress | [progress.md](progress.md) | Progress bar |
