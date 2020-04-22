# sys-apps/gnome-disk-utility

### elogid
Pass the `-Dlogind=libelogind` (`none` if this flag and `systemd` are disabled) option to the meson build command. Use the `libelogind` library to access seat information provided by the `elogind` daemon to avoid simultaneous device access by multiple users.

This flag should be enabled if the target system runs elogind daemon, e.g. for running GNOME desktop environment without SystemD.

### fat
Pull in the [sys-fs/dosfstools](../sys-fs/dosfstools.md) package as a dependency to provide an ability for GNOME Disk Utility to access FAT filesystems, e.g. create, mount, verify, etc.

It is recommended to enable this flag as the FAT filesystem is pretty widespread nowadays.

### gnome
Pass the `-Dgsd_plugin=true` option to the meson build command. Building and install the `gsd-disk-utility-notify` binary - a notification plugin for the GNOME Settings Daemon to report disk health failures (SMART status).

This flag should be enabled if the target system runs the GNOME desktop environment.

### systemd
Pass the `-Dlogind=libsystemd` (`none` if this flag and `elogind` are disabled) option to the meson build command. Use the `libsystemd` library to access seat information provided by the `logind` daemon to avoid simultaneous device access by multiple users.

This flag should be enabled if the target system runs SytemD as an init daemon.
