# app-crypt/p11-kit

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Use the Gtk-Doc tool to generate library API reference documentation from the source code in the HTML format and install it into the `/usr/share/gtk-doc/html` directory.

This flag should normally be disabled, because the documentation is primarily oriented towards the developers, not the end users.

### libffi
Pass the `-Dlibffi=enabled` option to the meson build script. Use a `libffi` library to build closures for PKCS#11 module and allow sharing them between multiple callers in the same process.

It is recommended to enable this module.

### nls
Pass the `-Dnls=true` option to the meson build script. Enable support for NLS (Native Language Support) to allow displaying informational, warning and error strings translated into the native language of the program's users, based on the system locale and configuration.

It is safe to disable this flag.

### systemd
Pass the `-Dsystemd=enabled` option to the meson build script. Install the SystemD service file to run a server process that exposes PKCS#11 module remotely and enable some code for socket-based activation. This allows an access to the locally attached Smart Card from the remote system.

This flag should normally be disabled.

### test
Execute the `meson test` command after the main build is completed to run the test suite provided with the source code and check for any regression. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
