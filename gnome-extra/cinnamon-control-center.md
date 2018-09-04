# gnome-extra/cinnamon-control-center

### colord
Pass a `--enable-color` option to a configure script. Build and install a `libcolor` library - a color management configuration panel for the Cinnamon control center that provides an ability to manage color profiles and associate them with various supported devices, e.g. displays, scanners, printers, etc.

This flag should be enabled if there is a need to deal with color profiled devices.

### cups
Pass a `--enable-cups` option to a configure script.

This flag does nothing and should be disabled.

### debug
Pass a `--enable-debug=yes` option to a configure script. Change compiler flags to include debugging symbols into produced libraries and binaries and disable compiler optimizations.

This flag should only be enabled for debugging purposes.

### systemd
Pass a `--enable-systemd` option to a configure script. This configure option is obsolete, because logind is a required dependency of the Cinnamon contorol center. The flag, however allows to switch between SystemD (when enabled) and elogind (when disabled) to satisfy this dependency.

This flag should be enabled if the target system uses SystemD init daemon.
