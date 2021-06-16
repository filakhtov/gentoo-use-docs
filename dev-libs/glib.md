# dev-libs/glib

### dbus
Enabling this flag will pull in the [gnome-base/dconf](../gnome-base/dconf.md) package as a dependency. This will enable a dconf GSettings backend required by certain applications to save their settings. If disabled, applications that require a GSettings backend will not be able to persist their settings between executions. See [Gentoo bug #498436](https://bugs.gentoo.org/498436) for more information.

It is recommended to enable this flag if the GNOME desktop environment or gnome applications are to be used on the target system.

### debug
Append the `-DG_ENABLE_DEBUG` option to the `CFLAGS` variable for the duration of the build to enable additional debugging code. When flag is disabled, append the `-DG_DISABLE_CAST_CHECKS` option instead to disable some additional sanity checks that are primarily useful for development builds.

This flag should be disabled and is only useful for testers, developers or for collecting a debugging information to report bugs.

### elf
Pass the `-Dlibelf=enabled` option to the meson build script. Use the `libelf` to provide an ability for the `gresource` tool to list and extract resources that are compiled into an `elf` file (a binary or a shared library). If this flag is disabled the `gresource` would only support resource files and if trying to use it on an `elf` file it will report the `gresource is built without elf support` error.

It is safe to disable this flag.

### fam
This flag passes the `-Dfam=true` option to the meson build script. The FAM (aka File Alteration Monitor) is used for filesystem monitoring in GIO modules and allows applications to react to changes, additions or deletions of files in a VFS.

This flag is not recommended on modern Kernels, because the same functionality is provided by the `inotify` nowadays.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Use the Gtk-Doc utility to generate reference documentation for the library in an HTML format, and install it into the `/usr/share/gtk-doc/html` directory.

It is normally safe to disable the flag, as generated documentation is only useful for developers, who works with the library.

### mime
The flag pulls in the [x11-misc/shared-mime-info](../x11-misc/shared-mime-info.md) package as a dependency. The package is used by the GIO xdgmime module for a file type detection. See [Gentoo bug #409481](https://bugs.gentoo.org/409481) for more details.

This flag is recommended to be enabled if the target system to be used with a desktop environment.

### selinux
Passes the `-Dselinux=enabled` option to the meson build script. This will provide an access to the SElinux context of various files through the GIO API.

This flag should only be enabled as part of the `selinux` Gentoo profile.

### static-libs
Pass the `-Ddefault_library=both` (`shared` when the flag is disabled) option to the meson build script. A build will produce statically linked libraries in additional to shared ones.

It is recommended to disable this flag, unless statically linked libraries are explicitly required for a development or other purposes.

### sysprof
Pass the `-Dsysprof=enabled` option to the meson build script. Enable support for sending profiling data to sysprof, e.g. from `Gsource.dispatch` events, D-Bus reads and writes, idle callbacks, etc,

This flag should only be enabled if there is a need to profile GLib based applications.

### systemtap
Passes the `-Ddtrace=true` and the `-Dsystemtap=true` options to the meson build script. First option enables static `dtrace` probes in compiled libraries, while second one enables `systemtap`. Tracing with the `systemtap` and the `dtrace` can provide a decent overview of the memory and the performance footprints for applications linked againts the GLib.

Enabling tracing has a small runtime overhead, so it is recommended to disable this flag unless tracing GLib is required.

### test
Pass the `-Dtests=true` option to the meson build script. Executes a `meson test` command after the build is complete to run a built-in test suite and check for regressions. Additional test dependencies will be installed. This will extend build time.

This flag should be disabled as it is only useful for the Gentoo team, developers or testers.

### utils
This flag does nothing in later versions of glib with Meson build system and should be disabled.

### xattr
Passes the `-Dxattr=true` option to the meson build script. Enables support for reading and manipulating extended files attributes for the GIO module.

It is recommended to enable this flag (even better if enabled system-wide), otherwise information stored in extended attributes might be lost.
