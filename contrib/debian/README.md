
Debian
====================
This directory contains files used to package yotokensd/yotokens-qt
for Debian-based Linux systems. If you compile yotokensd/yotokens-qt yourself, there are some useful files here.

## yotokens: URI support ##


yotokens-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install yotokens-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your yotokensqt binary to `/usr/bin`
and the `../../share/pixmaps/yotokens128.png` to `/usr/share/pixmaps`

yotokens-qt.protocol (KDE)

