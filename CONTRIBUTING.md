# Contributing to Elpis

Thanks for your interest in contributing! Here's everything you need to get started.

## Getting the code

```sh
git clone https://github.com/DavidMcFarlin/elpis.git
cd elpis
```

## Building locally

Elpis uses Flatpak for development builds.

```sh
flatpak-builder --force-clean --user --install --install-deps-from=flathub \
  build-flatpak flatpak/io.github.DavidMcFarlin.Elpis.json
flatpak run io.github.DavidMcFarlin.Elpis
```

You'll need Flatpak and the GNOME SDK installed. On Fedora/Ubuntu:

```sh
# Fedora
sudo dnf install flatpak flatpak-builder

# Ubuntu
sudo apt install flatpak flatpak-builder
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

## Running the test suite

The CI build runs tests inside the Flatpak sandbox:

```sh
flatpak-builder --force-clean --run build-flatpak \
  flatpak/io.github.DavidMcFarlin.Elpis.json python -m pytest
```

## Submitting a pull request

1. Fork the repo and create a branch off `main`.
2. Make your changes; keep commits focused and the message clear.
3. Update `CHANGELOG.md` under `[Unreleased]` for any user-visible change.
4. Open a PR — the CI build will run automatically.

## Coding style

- Python: follow [PEP 8](https://peps.python.org/pep-0008/). Run `flake8` before submitting.
- UI files: use `gtk4-builder-tool validate` to check `.ui` files.
- Keep changes narrowly scoped; avoid unrelated cleanups in the same PR.

## Reporting bugs

Use the [bug report template](.github/ISSUE_TEMPLATE/bug_report.yml) when opening an issue.
Include the Elpis version and any terminal output when running the app.

## Questions?

Open a [GitHub Discussion](https://github.com/DavidMcFarlin/elpis/discussions) for anything
that doesn't fit a bug report or feature request.
