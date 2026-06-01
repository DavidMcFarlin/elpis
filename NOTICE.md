# NOTICE

Elpis is a Pandora Radio client for the GNOME desktop, released under
the GNU General Public License version 3 (see `LICENSE`).

Elpis is a modified version of the Pithos project
(https://github.com/pithos/pithos), originally created by Kevin Mehall
and developed by a number of contributors between 2010 and 2024. The
Pithos source carried at the time of forking included contributions
from Kevin Mehall, Patrick Griffis, Brad Pitcher, Christopher Eby,
Steven Allen, Greg Sheremeta, Glenn Moss, and Jason Gray, among
others. Their copyright notices are preserved verbatim in the source
files they wrote.

## Modifications

Beginning in 2026, the codebase was modified by David McFarlin to
produce Elpis. The principal changes include:

- Port from GTK 3 to GTK 4
- Flatpak runtime upgrade to GNOME 50
- Removal of the expired bundled Pandora CA certificate; TLS now
  uses the system trust store
- Network-error handling refresh for modern Python
- Additional Pandora API surfaces exposed in the UI: genre station
  browser, station seed manager, station sharing, bookmarks viewer,
  right-click station context menu, "Why is this playing?"
- Rebrand under the application ID `io.github.DavidMcFarlin.Elpis`

Detailed history is available in the git log.

Elpis is not affiliated with or endorsed by either Pandora Media, Inc.
or the upstream Pithos project.
