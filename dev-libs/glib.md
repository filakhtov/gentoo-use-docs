# dev-libs/glib
### dbus
Enabling this flag will pull in the [gnome-base/dconf](../gnome-base/dconf.md) package as a dependency. This will enable a dconf GSettings backend required by certain applications to save their settings. If disabled, applications that require a GSettings backend will not be able to persist their settings between executions. See [Gentoo bug #498436](https://bugs.gentoo.org/498436) for more information.

It is recommended to enable this flag if the GNOME desktop environment or gnome applications are to be used on the target system.

### debug
Passes the `--enable-debug=yes` option to the configure script. This appends the `-g` flag to the `CFLAGS` variable to build libraries with debugging symbols. It will also define a `G_ENABLE_DEBUG` C macro to enable additional debugging code.

This flag should be disabled and is only useful for testers, developers or for collecting a debugging information to report bugs.

### fam
This flag passes the `--enable-fam` option to the configure script. The FAM (aka File Alteration Monitor) is used for filesystem monitoring in GIO modules and allows applications to react to changes, additions or delitions of files in a VFS.

This flag is not recommended on modern Kernels, because the same functionality is provided by the `inotify` nowadays.

### mime
The flag pulls in the [x11-misc/shared-mime-info](../x11-misc/shared-mime-info.md) package as a dependency. The package is used by the GIO xdgmime module for a file type detection. See [Gentoo bug #409481](https://bugs.gentoo.org/409481) for more details.

This flag is recommended to be enabled if the target system to be used with a desktop environment.

### selinux
Passes the `--enable-selinux` option to the configure script. This will provide an access to the SElinux context of various files through the GIO API.

This flag should only be enabled as part of the `selinux` Gentoo profile.

### static-libs
The flag passes the `--enable-static` option to the configure script. A build will produce statically linked libraries.

It is recommended to disable this flag, unless statically linked libraries are required for a development or other purposes.

### systemtap
Passes the `--enable-dtrace` and the `--enable-systemtap` options to the configure script. First option enables static `dtrace` probes in compiled libraries, while second one enables `systemtap`.

Tracing with the `systemtap` and the `dtrace` can provide a decent overview of the memory and the performance footprints for applications linked againts the GLib.

Enabling tracing has a small runtime overhead, so it is recommended to disable this flag unless tracing GLib is required.

### test
Executes a `make check` command after the build is complete and runs a built-in test suite. Additional test dependencies will be installed. This will extend build time.

This flag should be disabled as it is only useful for the Gentoo team, developers or testers.

### utils
The flag passes the `--enable-libelf` option to the configure script. This will link the `gresource` tool against the `libelf` and provide a support for resources extraction from ELF binaries and libraries.

It is safe to disable this flag unless there is a plan to extract resources from ELF files.

### xattr
Passes the `--enable-xattr` option to the configure script. Enables support for reading and manipulating extended files attributes for the GIO module.

It is recommended to enable this flag (even better if enabled system-wide), otherwise information stored in extended attributes might be lost.
