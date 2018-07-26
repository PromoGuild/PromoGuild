
Debian
====================
This directory contains files used to package promoguildd/promoguild-qt
for Debian-based Linux systems. If you compile promoguildd/promoguild-qt yourself, there are some useful files here.

## promoguild: URI support ##


promoguild-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install promoguild-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your promoguildqt binary to `/usr/bin`
and the `../../share/pixmaps/promoguild128.png` to `/usr/share/pixmaps`

promoguild-qt.protocol (KDE)

