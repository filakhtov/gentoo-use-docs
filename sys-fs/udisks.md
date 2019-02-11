# sys-fs/udisks

### acl
Pass the `--enable-acl` option to the configure script. Set the ACL (Access Control List) read permissions on target mount point directories.

It is recommended to enable this flag if the filesystem that hosts mount point supports ACLs.

### debug
Pass the `--enable-debug` option to the configure script. Enable printing of the additional debugging messages at runtime.

This flag should only be enabled if there is a need to debug any problems with Udisks.

### elogind
Pull in the [sys-auth/elogind](../sys-auth/elogind.md) package as a dependency that provides `libelogind` library used for associating a disk mount with a particular user session seat to automatically unmount it when the user logs out.

This flag should be enabled if the target system uses elogind as a session manager.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate the `UDisks-2.0.gir` GIR metadata file to provide dynamic bindings to the `libudisks2` library for languages other than C via the GObject introspection.

It is safe to disable the flag.

### lvm
Pass the `--enable-lvm2` and the `--enable-lvmcache` options to the configure script. Build and install the `libudisks2_lvm2` library that provides an ability to list, mount and manage LVM (Logical Volume Manager) partitions.

This flag should be enabled if there is a need to access LVM partitions through Udisks.

### nls
Pass the `--enable-nls` option to the configure script. Use the `intltool` to provide an ability to translate programs messages into different languages based on the system locale settings.

It is safe to disable the flag, unless there is a need to use Udisks in languages other than English.

### selinux
Pull in the [sec-policy/selinux-devicekit](../sec-policy/selinux-devicekit.md) package that provides SELinux policies necessary for Udisks to properly operate under a SELinux-restricted kernel.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### systemd
Use the `libsystemd-login` library to provide an ability to associate disk mounts with a particular user session seat via SystemD loginD, to automatically unmount them when the user finishes a session, i.e. logs out.

This flag should be enabled if the target system uses SystemD as an init system.

### vdo
Pass the `--enable-vdo` option to the configure script. Build and install the `libudisks2_vdo` library that provides an ability to create new and activate or start existing VDO (Virtual Data Optimizer) compressed volumes.

This flag should normally be disabled, unless there is an explicit need to manage VDO volumes.
