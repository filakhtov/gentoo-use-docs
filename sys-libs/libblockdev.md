# sys-libs/libblockdev

### bcache
Only makes sense if the `kbd` flag is also enabled. Pass the `--with-bcache` option to the configure script. Enable support for bcache - a Linux kernel block layer cache that allows one or more fast disk drives to act as a cache for slower disk drives for KBD (Kernel Block Devices) plugin.

This flag should be enabled if there is a need to deal with bcache subsystem.

### cryptsetup
Pass the `--with-crypto` option to the configure script. Build and install the `libbd_crypto` library - a `libblockdev` plugin for operations with encrypted devices (currently only LUKS devices are supported).

This flag should be enabled if there is a need to deal with LUKS-encrypted partitions.

### device-mapper
Pass the `--with-dm` option to the configure script. Build and install the `libbd_dm` library - a `libblockdev` plugin for basic operations with device mapper's "linear" targets, including creating and removing them.

This flag should be enabled if integration with device mapper framework is desired.

### dmraid
Only works if the `device-mapper` flag is enabled. Pass the `--with-dmraid` option to the configure script. Extend the `libbd_dm` plugin library to provide an ability to manage `dm-raid` (Device-Mapper's RAID) devices, e.g. create, delete, activate, etc, by utilizing the `libdmraid` library.

This flag should be enabled if there is a need to manage DM RAID devices using the library.

### escrow
Pass the `--with-escrow` option to the configure script. Add an additional feature to the `libbd_crypto` cryptography plugin library (see the `cryptsetup` flag for details) that provides an ability to create recovery encryption keys for an encrypted volume in the so-called escrow storage which can be used to access encrypted data if the main passphrase is lost or forgotten.

It is safe to disable this flag, however it is highly recommended to use some alternative recovery key creation and storage mechanism.

### gtk-doc
Pass the `--with-gtk-doc` option to the configure script. Use the Gtk-Doc tool to generate library API documentation from the source code annotation and install it into the `/usr/share/doc/libblockdev-<VERSION>` directory.

It is safe to disable the flag.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `BlockDev-2.0.gir` GIR metadata file to provide dynamic bindings for `libblockdev` library to languages other than C using the GObject introspection framework.

This flag can be safely disabled.

### kbd
Pass the `--with-kbd` option to the configure script. Build and install the `libbd_kbd` library - a `libblockdev` plugin providing the functionality related to KBD (kernel block devices, namely zRAM and bcache): querying stats; creating and destroying bcache/zRAM devices; attaching, detaching and modifying caching mode for bcache devices, etc.

This flag should be enabled if there is a need to deal with KBD.

### lvm
Pass the `--with-lvm` and the `--with-lvm-dbus` options to the configure script. Build and install the `libbd_lvm` library - a plugin that provide the LVM-related functionality by direct calls to LVM2 tools, and `libbd_lvm2-dbus` - to utilize the LVM DBus API. This includes reading data, creating, deleting, resizing and other management operations on PVs/VGs/LVs (where appropriate).

This flag should be enabled if there is a need to deal with LVM devices.

### test
Pass the `--enable-tests` option to the configure script. Execute the `make check` command after the main build is completed to run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled, it is mainly used by the Gentoo team, testers and developers.

### tools
Pass the `--with-tools` option to the configure script. Build and install the `lvm-cache-stats` tool - a small utility to display various information about the LVM volume group, such as logical volume sizes, cache sizes, read and write cache statistics, etc, both in human-readable and JSON formats.

It is safe to disable this flag.

### vdo
Pass the `--with-vdo` option to the configure script. Build and install the `libbd_vdo` library - a `libblockdev` plugin that provides an ability to operate on VDO (Virtual Data Optimizer) compressed volumes, including parsing information, creating, removing, activating and deactivating volumes, changing compression and deduplication status, etc.

This flag should normally be disabled, and should only be enabled if there is an explicit need to manipulate VDO volumes.
