# gnome-extra/cinnamon-control-center

### colord
Pass the `-Dcolor=true` option to the `meson` build script. Build and install a `libcolor` library - a color management configuration panel for the Cinnamon control center that provides an ability to manage color profiles and associate them with various supported devices, e.g. displays, scanners, printers, etc.

This flag should be enabled if there is a need to deal with color profiled devices.

### modemmanager
Pass the `-Dmodemmanager=true` option to the `meson` build script. Enable support for the ModemManager and provide an ability to manage modem devices in Cinnamon Control Center, e.g. checking the status, setting them up, etc.

This flag can be safely disabled if there is no need to deal with modems.

### networkmanager
Pass the `-Dnetworkmanager=true` option to the `meson` build script. Enable support for NetworkManager to provide an ability to manage network devices and connections via Cinnamon Control Center, e.g. enabling and disabling wireless adapter, connecting to wireless network, configuring IP addresses, etc.

It is safe to disable this flag if there is no need to use CCC for network management.

### systemd
Cinnamon Control Center (CCC) requires logind to properly operate. When this flag is enabled, the [sys-apps/systemd](../sys-apps/systemd.md) package will be pulled as a dependency and CCC will use systemd's settings interface (localed, timedated, hostnamed, etc). If, however, this flag is disabled, the [app-admin/openrc-settingsd](../app-admin/openrc-settingsd) dependency will be used instead and CCC will use OpenRC-based implementation instead.

This flag should be enabled if the target system uses systemd init daemon.

### test
Start a new Xvfb session and execute the `meson test` command inside of it when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

The flag should normally be disabled, as it is mainly targeted for the maintainers, testers and developers.

