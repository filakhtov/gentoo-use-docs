# gnome-extra/cinnamon-settings-daemon

### colord
Pass a `-Duse_color=enabled` option to the `meson` build script. Integrate with the colord daemon to provide an ability to associate color profiles with different devices, such as diplay, and automatically apply them when devices are connected, disconnected or changed.

This flag should be enabled if there is a need to interact with color profiles.

### cups
Pass a `-Duse_cups=enabled` option to the `meson` build script. Integrate with a CUPS (Common Unix Printing System) to monitor printers, printing queues and jobs to generate notifications when their status changes.

This flag should be enabled if it is desired to receive printing notifications.

### smartcard
Pass a `-Duse_smartcard=enabled` option to the `meson` build script. Build and install a `csd-smartcard` daemon - a Cinnamon Settings Daemon Smartcard plugin that monitors smart card insertion and removal, and provides an ability for Cinnamon ecosystem to read data from and write data to security cards.

This flag should be enabled if there is a need to use smart cards.

### systemd
Cinnamon Settings Daemon depends on logind, so when enabled, pull in a [sys-apps/systemd](../sys-apps/systemd.md) package to satisfy this dependency. When disabled, a [sys-auth/elogind](../sys-auth/elogind.md) will be pulled instead.

This flag should be enabled if the target system runs a SystemD init process.

