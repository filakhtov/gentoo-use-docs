# sys-apps/gnome-disk-utility

### fat
Pull in the [sys-fs/dosfstools](../sys-fs/dosfstools.md) package as a dependency to provide an ability for GNOME Disk Utility to access FAT filesystems, e.g. create, mount, verify, etc.

It is recommended to enable this flag as the FAT filesystem is pretty widespread nowadays.

### gnome
Pass the `--enable-gsd-plugin` option to the configure script. Building and install the `gsd-disk-utility-notify` binary - a notification plugin for the GNOME Settings Daemon to report disk health failures (SMART status).

This flag should be enabled if the target system runs the GNOME desktop environment.

### systemd
Pass the `--enable-libsystemd` option to the configure script. Use the `libsystemd` library to access seat information provided by the `logind` daemon to avoid simultaneous device access by multiple users.

This flag should be enabled if the target system runs SytemD as an init daemon.
