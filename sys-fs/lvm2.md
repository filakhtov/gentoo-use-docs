# sys-fs/lvm2
### clvm
Pass the `--with-cluster=shared`, the `--with-clvmd=none` and the `--with-pool=shared` options to the configure script. Build and install `clvmd` - a cluster LVM daemon and appropriate init files.

This flag should be disabled unless there is a need to run clustered LVM.

### cman
The flag only works if the `clvm` flag is also enabled. Pass the `cman` value instead of `none` for the `--with-clvmd` option of configure script. Enable CMAN (Cluster MANager) that provides the low-level infrastructure for the clustered LVM, e.g. node communications, votes, quorum, etc.

This flag should be disabled unless there is a need to run clustered LVM.

### corosync
The flag only works if the `clvm` flag is also enabled. Append a `corosync` value to the `--with-clvmd` option of configure script. Use Corosync as a messaging layer between cluster members.

This flag should be disabled if there is no need to run clustered LVM.

### device-mapper-only
Pass the `--disable-udev-systemd-background-jobs` option to the configure script. Pass a `none` value to the `--with-mirrors` and the `--with-snapshots` options. Build a package using a `make device-mapper` command and only install device-mapper binary. Do not install init scripts and configuration files.

It is safe to disable this flag. It can be useful for embedded systems.

### lvm1
Pass the `--with-lvm1` option with a `shared` (`none` if disabled) value to the configure script. Provide support for an LVM version 1.

This flag should only be enabled if there is an explicit requirement to work with LVM1.

### lvm2create_initrd
Install an `lvm2create_initrd` tool - a tool to create initial ramdisk (initrd) image suitable for booting systems with a root partition on LVM.

This flag should normally be disabled as it is obsolete and does not even work with Gentoo.

### openais
The flag only works if the `clvm` flag is also enabled. Append an `openais` value to the `--with-clvmd` option of the configure script. Use OpenAIS extension to Corosync that provides support for clustered filesystems, e.g. GFS2 and OCFS2.

This flag should be disabled if there is no need to support clustered LVM.

### readline
Pass the `--enable-readline` option to the configure script. Enable support for an LVM shell. Provide a history support using a GNU Readline library.

It is safe to disable this flag.

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
Pass the `--enable-udev-systemd-background-jobs` option to the configure script. Enable integration with an udev SystemD protocol, install unit files and generators.

It is recommended to toggle this flag system-wide, e.g. as part of a SystemD Portage profile.

### thin
Pass the `--with-thin=internal` and the `--with-cache=internal` options to the configure script. Pass a destination installation path to the `--with-thin-check`, `--with-thin-dump`, `--with-thin-repair`, `--with-thin-restore`, `--with-cache-check`, `--with-cache-dump`, `--with-cache-repair`, `--with-cache-restore`. Enable support for Thinly Provisioned Logical Volumes. Provide a `-T` runtime option for an `lvcreate` command.

This flag should be disabled unless there is a need to manage Thin LVM.

### udev
Enable udev sync support to ensure that parallel udev rules processing aren't conflicting and e.g. not removing a device node that might be handling another event at the same time.

It is recommended to enable this flag to avoid various synchronisation issues.
