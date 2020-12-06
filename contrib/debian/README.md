
Debian
====================
This directory contains files used to package diablod/diablo-qt
for Debian-based Linux systems. If you compile diablod/diablo-qt yourself, there are some useful files here.

## diablo: URI support ##


diablo-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install diablo-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your diabloqt binary to `/usr/bin`
and the `../../share/pixmaps/diablo128.png` to `/usr/share/pixmaps`

diablo-qt.protocol (KDE)

