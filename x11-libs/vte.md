# x11-libs/vte

### crypt
Pass the `-Dgnutls=true` option to the meson build command. Use the GnuTLS library to encrypt terminal's scrollback buffer if there is a need to write its contents to the temporary directory on the local filesystem, e.g. when buffer is too big to be held in memory. When disabled, a message `GNUTLS not enabled; data will be written to disk unencrypted!` will be printed into a terminal window at startup.

This flag should be enabled for increased security, however might be an unnecessary overhead if temporary file system is stored in the volatile memory, such as `tmpfs`.

### debug
Pass the `-Ddebugg=true` option to the meson build command. Enable extra debugging checks and logging messages that are performed at runtime.

This flag should only be enabled if there is a need to debug the library.

### introspection
Pass the `-Dgir=true` option to the meson build command. Generate and install the `Vte-2.91.gir` GIR metadata file to provide bindings for the `libvte` library to languages other than C using the GObject Introspection framework.

This flag can be safely disabled.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `-Dvapi=true` option to the meson build command. Generate and install the `vte-2.91.vapi` Vala bindings file for the `libvte` library.

It is safe to disable the flag.

### vanilla
Do not apply Gentoo-specific patches and build vanilla code. This is necessary if there is a need to report bugs to an upstream maintainer.

This flag should normally be enabled.
