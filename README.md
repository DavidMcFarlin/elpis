# Elpis

A native Pandora Radio client for the GNOME desktop.

Elpis is GTK 4-based, Flatpak-friendly, and integrates with desktop features
like media keys, MPRIS, last.fm scrobbling, and the system notification area.

## Features

- Stream Pandora stations and discover new ones with the built-in genre
  browser
- Add, remove, and edit station seeds (songs, artists, genres) without
  leaving the app
- Right-click any station for quick actions: listen, info, edit seeds,
  share, delete
- Bookmark songs and artists; view and manage bookmarks in-app
- See *why* a track is playing — Pandora's track-explanation traits are
  one click away
- Media keys, MPRIS, last.fm scrobbling

## Install

### Flatpak (recommended for daily use)

Until Elpis is published on Flathub, build and install locally:

```sh
flatpak-builder --force-clean --user --install --install-deps-from=flathub \
  build-flatpak flatpak/io.github.DavidMcFarlin.Elpis.json
flatpak run io.github.DavidMcFarlin.Elpis
```

### From source

Requirements: `meson`, `ninja`, GTK 4 (≥ 4.10), Python 3.10+, PyGObject,
GStreamer 1.0, libsecret. Optional: `pylast` for last.fm scrobbling.

```sh
meson setup --prefix=$HOME/.local build
meson install -C build
glib-compile-schemas $HOME/.local/share/glib-2.0/schemas
elpis
```

## Configuration

Elpis stores account credentials in the system keyring via libsecret —
nothing is written to disk in plaintext. Settings live under
`io.github.DavidMcFarlin.Elpis` in GSettings (visible in `dconf-editor`
if you want to inspect or reset them).

## Reporting issues

Please use [GitHub Issues](https://github.com/DavidMcFarlin/elpis/issues).
Include your distribution, GTK version, and a copy of the log
(`elpis --debug` reproduces with verbose output to the terminal).

## License

GPL-3.0. See [`LICENSE`](LICENSE).

Elpis descends from the [Pithos](https://github.com/pithos/pithos) project;
see [`NOTICE.md`](NOTICE.md) for the relationship and a summary of
modifications introduced by this fork.

Elpis is not affiliated with or endorsed by Pandora Media, Inc.
