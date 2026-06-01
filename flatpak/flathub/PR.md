# Flathub submission: Elpis (`io.github.DavidMcFarlin.Elpis`)

> Open this as a PR against the **`new-pr`** branch of `flathub/flathub`,
> from a branch named exactly `io.github.DavidMcFarlin.Elpis`, containing
> the manifest `io.github.DavidMcFarlin.Elpis.json` at the repo root.

---

## Title

```
Add io.github.DavidMcFarlin.Elpis
```

## Description

Elpis is a native GTK 4 client for Pandora Radio, descended from Pithos
1.6.2. It plays stations, rates tracks, manages stations/seeds, browses
genres, and integrates with the desktop via MPRIS, media keys, a tray
icon, and last.fm scrobbling.

- **Upstream / source:** https://github.com/DavidMcFarlin/elpis
- **License:** GPL-3.0-or-later (metadata CC0-1.0)
- **Runtime:** `org.gnome.Platform` 50

I am the developer of this application and the maintainer of the upstream
repository.

### Submission checklist

- [x] The app ID follows the rules — `io.github.DavidMcFarlin.Elpis` uses
      the `io.github.<user>` prefix and I control the GitHub account
      `DavidMcFarlin`.
- [x] The manifest builds from a tagged, pinned source
      (`git` tag `1.6.3`, commit `38c111828be69abead95d1a1abc4d99844b485f1`).
- [x] All sources are pinned with `sha256` (pylast + deps, keybinder) or a
      commit hash (the app itself).
- [x] No network access during the build (Python deps installed offline
      from pinned wheels/sdist).
- [x] AppStream metainfo validates (`appstreamcli validate`) and includes
      a screenshot, OARS content rating, release notes, and branding.
- [x] `flatpak-builder-lint manifest` passes with no findings.
- [x] A full build from the tag passes `flatpak-builder-lint repo` apart
      from the expected `appstream-external-screenshot-url` /
      `appstream-screenshots-not-mirrored-in-ostree` findings, which the
      Flathub pipeline resolves by mirroring the screenshot server-side.
- [x] Minimal permissions: `network` (Pandora API), `pulseaudio`,
      `wayland` + `fallback-x11`, `ipc`, dconf migration, and `--talk-name`
      for media keys (GNOME/MATE settings daemon) and the StatusNotifier
      tray.

### Notes for reviewers

- `--share=network` is required: Pandora is a streaming service, so the
  app needs network access to authenticate and stream audio.
- The `--talk-name` entries are for hardware media-key handling
  (`org.gnome.SettingsDaemon.MediaKeys`, `org.mate.SettingsDaemon`) and the
  optional tray icon (`org.kde.StatusNotifierWatcher`).
- `keybinder` is bundled for X11 global media-key fallback; it is inert
  under Wayland.
