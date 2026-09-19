# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-09-19

### Added

- GitHub high contrast palette for bb light and dark mode.
- `github-light-high-contrast` and `github-dark-high-contrast` code themes via `theme.json`.
- Per-state colors for sidebar thread indicators (failed, needs input, queued, working, background work, plan mode and goal, unread success, draft), each at 11:1 or higher contrast against the canvas.
- `--primary` at 11:1 or higher contrast against the canvas in both modes.
- Larger unread-success dot (8px) and thicker working spinner stroke (2.5).

### Removed

- Opacity mask on animated sidebar indicators, so they render at full color.
