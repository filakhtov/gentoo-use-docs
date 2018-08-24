# sys-libs/libblockdev

### bcache
Only makes sense if the `kbd` flag is also enabled. Pass the `--with-bcache` option to the configure script. Enable support for bcache - a Linux kernel block layer cache that allows one or more fast disk drives to act as a cache for slower disk drives for KBD (Kernel Block Devices) plugin.

This flag should be enabled if there is a need to deal with bcache subsystem.

### cryptsetup
Pass the `--with-crypto` option to the configure script. Build and install the `libbd_crypto` library - a `libblockdev` plugin for operations with encrypted devices (currently only LUKS devices are supported).

This flag should be enabled if there is a need to deal with LUKS-encrypted partitions.

### dmraid
Pass the `--with-dm` option to the configure script. Build and install the `libbd_dm` library - a `libblockdev` plugin for basic operations with device mapper, e.g. discovering RAID sets, get RAID members, activate and deactivate RAID arrays, etc.

This flag should be enabled if integration with device mapper is desired.

### doc
Pass the `--with-gtk-doc` option to the configure script. Use the Gtk-Doc tool to generate library API documentation from the source code annotation and install it into the `/usr/share/doc/libblockdev-<VERSION>` directory.

It is safe to disable the flag.

### kbd
Pass the `--with-kbd` option to the configure script. Build and install the `libbd_kbd` library - a `libblockdev` plugin providing the functionality related to KBD (kernel block devices, namely zRAM and bcache): querying stats; creating and destroying bcache/zRAM devices; attaching, detaching and modifying caching mode for bcache devices, etc.

This flag should be enabled if there is a need to deal with KBD.

### lvm
Pass the `--with-lvm` and the `--with-lvm-dbus` options to the configure script. Build and install the `libbd_lvm` library - a plugin that provide the LVM-related functionality by direct calls to LVM2 tools, and `libbd_lvm2-dbus` - to utilize the LVM DBus API. This includes reading data, creating, deleting, resizing and other management operations on PVs/VGs/LVs (where appropriate).

This flag should be enabled if there is a need to deal with LVM devices.

### test
Pass the `--enable-tests` option to the configure script. Execute the `make check` command after the main build is completed to run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled, it is mainly used by the Gentoo team, testers and developers.
