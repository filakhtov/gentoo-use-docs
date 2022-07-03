# app-crypt/gcr

### gtk
Pass the `-Dgtk=true` option to the meson build command. Build and install the `gcr-viewer` - a certificate and key viewer written in GTK and the `gcr-prompter` - prompt dialog for crypto related UI tasks.

It is safe to disable the flag.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build command. Use the Gtk-Doc tool to generate the reference manual for gcr and gck libraries in the HTML format from the source-code annotations and install it into the system.

This flag should only be enabled if there is a need to install development documentation for these libraries.

### introspection
Pass the `-Dintrospection` option to the meson build command. Generate and install `Gck-1.gir`, `Gcr-3.gir` (and `GcrUi-3.gir` if the `gtk` flag is enabled)GIR metadata files to provide dynamic bindings for the gcr and gck libraries to languages other than C using the GObject introspection framework.

This flag can be safely disabled.

### systemd
Pass the `-Dsystemd=enabled` option to the meson build command. Install the systemd `.service` and `.socket` files for the `gcr-ssh-agent` daemon to allow socket-based agent activation and enable additional code in the daemon itself to properly support this mode of operation.

This flag should only be enabled on systems that use systemd init daemon.

### test
Start a new D-Bus session and execute the `meson test` command inside of it when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend a build time.

The flag should normally be disabled. It is mainly targeted to maintainers, testers and developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `-Dvapi=true` option to the configure script. Generate `gck-1.vapi`, `gcr-3.vapi`, `pkcs11.vapi` (and `gcr-ui-3.vapi` if the `gtk` flag is enabled) Vala language bindings for gcr and gck libraries.

It is safe to disable this flag.
