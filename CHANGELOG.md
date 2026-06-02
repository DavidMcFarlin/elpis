# Changelog

All notable changes to Elpis are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added
- Flathub submission manifest and PR draft

## [1.6.3] — 2026

### Changed
- App screenshot added for store listing
- Metadata and manifest prepared for Flathub submission
- Wayland `app_id` pinned to fix missing taskbar icon
- App icon squared to 164×164
- README expanded with full project description
- Elpis theme applied; headerbar restructured
- About dialog refreshed; symbolic icon placeholder added
- Rebranded from Pithos to Elpis

### Infrastructure
- CI upgraded to flatpak-github-actions v6 with GNOME 50 image
- Flatpak runtime bumped to GNOME 50
- Renamed `appdata.xml` → `metainfo.xml`
- GTK4 UI validation added via `gtk4-builder-tool`
- `typing-extensions` and `setuptools-scm` vendored for pylast build

[Unreleased]: https://github.com/DavidMcFarlin/elpis/compare/1.6.3...HEAD
[1.6.3]: https://github.com/DavidMcFarlin/elpis/releases/tag/1.6.3
