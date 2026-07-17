# Changelog

All notable changes to Elpis are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added
- Light and dark themes: follow the system color scheme by default, with a
  Theme submenu (System / Light / Dark) in the main menu backed by a new
  `theme` GSetting
- Flathub submission manifest and PR draft

### Fixed
- Tray icon no longer blank under Flatpak: the StatusNotifier item now
  ships its icon as ARGB pixel data (`IconPixmap`) so the host tray shows
  it even when it cannot resolve the sandboxed icon name

### Changed
- UI redesigned platform-native on libadwaita: the custom dark "aurora" skin
  (purple gradients, glow shadows, pill controls) is replaced by the Adwaita
  stylesheet and the system accent color
- Track rows now use a clear type hierarchy (bold title, plain artist, dimmed
  album and status) and the brand tile was removed from the header bar
- Placeholder album art re-derives its colors when the theme switches
- New app icon: a hand-drawn flat vector of the spark of hope above
  Pandora's jar (a pithos), replacing the gradient wordmark tile; the
  full icon set (symbolic, tray, mono variants) shrinks from ~1.2 MB of
  embedded rasters to ~2 KB of real SVG, and store branding colors move
  from lavender to terracotta to match

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
