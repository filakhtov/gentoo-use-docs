# gnome-extra/cinnamon-control-center

### colord
Pass the `--enable-color` option to the configure script. Build and install a `libcolor` library - a color management configuration panel for the Cinnamon control center that provides an ability to manage color profiles and associate them with various supported devices, e.g. displays, scanners, printers, etc.

This flag should be enabled if there is a need to deal with color profiled devices.

### debug
Pass the `--enable-debug=yes` option to the configure script. Change compiler flags to include debugging symbols into produced libraries and binaries and disable compiler optimizations.

This flag should only be enabled for debugging purposes.

### modemmanager
Pass the `--enable-modemmanager` option to the configure script. Enable support for the ModemManager and provide an ability to manage modem devices in Cinnamon Control Center, e.g. checking the status, setting them up, etc.

This flag can be safely disabled if there is no need to deal with modems.

### networkmanager
Pass the `--enable-networkmanager` option to the configure script. Enable support for NetworkManager to provide an ability to manage network devices and connections via Cinnamon Control Center, e.g. enabling and disabling wireless adapter, connecting to wireless network, configuring IP addresses, etc.

It is safe to disable this flag if there is no need to use CCC for network management.

### systemd
Cinnamon Control Center (CCC) requires logind to properly operate. When this flag is enabled, the [sys-apps/systemd](../sys-apps/systemd.md) package will be pulled as a dependency and CCC will use systemd's logind. If, however, this flag is disabled, the [sys-auth/elogind](../sys-auth/elogind.md) dependency will be used instead and CCC will use elogind instead.

This flag should be enabled if the target system uses systemd init daemon.
