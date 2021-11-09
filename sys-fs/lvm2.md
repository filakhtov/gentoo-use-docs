# sys-fs/lvm2

### device-mapper-only
Pass the `--disable-udev-systemd-background-jobs` option to the configure script. Pass a `none` value to the `--with-mirrors` and the `--with-snapshots` options. Build a package using a `make device-mapper` command and only install device-mapper binary. Do not install init scripts and configuration files.

It is safe to disable this flag. It can be useful for embedded systems.

### lvm2create-initrd
Install an `lvm2create_initrd` tool - a tool to create initial ramdisk (initrd) image suitable for booting systems with a root partition on LVM.

This flag should normally be disabled as it is obsolete and does not even work with Gentoo.

### readline
Pass the `--enable-readline` option to the configure script. Enable support for an LVM shell. Provide a history support using a GNU Readline library.

It is safe to disable this flag.

### sanlock
Pass the `--enable-lvmlockd-sanlock` option to the configure script. Enable support for the `sanlock` type locking for the `lvmlockd` daemon, that is used to place locks on disk within LVM storage, in order to provide shared storage to the volume groups to multiple hosts.

This flag should normally be disabled as it is primarily useful to provide shared logical volumes in virtualization or storage cluster applications.

### selinux
Pass the `--enable-selinux` option to the configure script. Enable an ability to run with a SELinux enabled. Provide an ability to set a SELinux context for LVM device mapper nodes.

This flag should only be ever toggled system-wide, e.g. as part of the SELinux-enabled portage profile.

### static
Pass the `--enable-static_link` option to the configure script. Change a value of the `--with-lvm1` option to `internal` if the `lvm1` flag is enabled and value of the `--with-cluster` and the `--with-pool` options to `internal` if the `clvm` flag is enabled. Build and install statically linked binaries, e.g. an `lvm` and a `dmsetup` with a `.static` suffix appended.

This flag should be disabled unless there is an explicit need for the static binaries.

### static-libs
Build and install statically linked a `libdevmapper.a` library. If the `device-mapper-only` flag is disabled also build and install a `libdaemonclient.a` and a `libdevmapper-event.a` libraries.

This flag should be disabled unless there is an explicit need for the static libraries, e.g. for development purposes.

### systemd
Pass the `--enable-udev-systemd-background-jobs` and `--enable-notify-dbus` options to the configure script. Enable integration with an udev SystemD protocol, install unit files and generators, and provide an ability to send D-Bus notifications for various events.

It is recommended to toggle this flag system-wide, e.g. as part of a SystemD Portage profile.

### thin
Pass the `--with-thin=internal` and the `--with-cache=internal` options to the configure script. Pass a destination installation path to the `--with-thin-check`, `--with-thin-dump`, `--with-thin-repair`, `--with-thin-restore`, `--with-cache-check`, `--with-cache-dump`, `--with-cache-repair`, `--with-cache-restore`. Enable support for Thinly Provisioned Logical Volumes. Provide a `-T` runtime option for an `lvcreate` command.

This flag should be disabled unless there is a need to manage Thin LVM.

### udev
Pass the `--enable-udev_rules` and `--enable-udev_sync` options to the configure script. Enable udev sync support and install appropriate rules to ensure that parallel udev rules processing aren't conflicting and e.g. not removing a device node that might be handling another event at the same time.

It is recommended to enable this flag to avoid various synchronisation issues.
