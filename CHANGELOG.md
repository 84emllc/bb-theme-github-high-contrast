# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- 84EM brand colors for thread pane focus state. Dark mode: focused pane background `#090e1e` (obsidian), unfocused pane background `#000000`, unfocused pane borders `#5e7089` (slate-500).
- Split pane title pill: focused `#004c7e` (brand navy) with white text, unfocused `#b54600` (brand orange) with white text.
- Prompt box border at 2px: focused `#58a6ff` (AA navy), unfocused `#b54600` (brand orange).
- Prompt box send button: focused `#58a6ff` with obsidian text, unfocused `#e8935a` (AA orange) with obsidian text.
- Right panel tabs: active tab filled with `--primary` and `--primary-foreground`; inactive tabs use `--muted-foreground` with a 1px `--border` outline.
- Thread header shows a 2px bottom line in `#9ff400` (brand green) while a run is active (keyed on the Stop run button).
- Thread header status glyph (bb 0.45.0+) renders working states (thread working, working with draft, workflow, background agent, background command, plan mode, goal) in `#9ff400` (brand green) in dark mode. Sidebar indicators and light mode keep their `--ind-*` colors.

### Changed

- `--border-seam`, `--border-hairline`, and `--sidebar-border` now match `--border` in both modes, so pane seams, hairline separators, and sidebar borders are high contrast too.

## [1.0.0] - 2026-09-19

### Added

- GitHub high contrast palette for bb light and dark mode.
- `github-light-high-contrast` and `github-dark-high-contrast` code themes via `theme.json`.
- Per-state colors for sidebar thread indicators (failed, needs input, queued, working, background work, plan mode and goal, unread success, draft), each at 11:1 or higher contrast against the canvas.
- `--primary` at 11:1 or higher contrast against the canvas in both modes.
- Larger unread-success dot (8px) and thicker working spinner stroke (2.5).

### Removed

- Opacity mask on animated sidebar indicators, so they render at full color.
