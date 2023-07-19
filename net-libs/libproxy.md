# net-libs/libproxy

### duktape
Pass the `-Dpacrunner-duktape=true` and `-Dcurl=true` options to the Meson build script. Use the Duktape embeddedable JavaScript engine as a backend to interpret PAC (Proxy Auto-Configuration) files.

It is safe to disable this flag if there is no need to use PAC files with `libproxy`.

### gnome
Pass the `-Dconfig-gnome=true` option to the Meson build script. Build the plugin to integrate with Gnome desktop environment and be able to query GSettings configuration backend for proxy configuration information.

This flag should be enabled if the target system is running a GNOME 3 based desktop environment.

### gtk-doc
Pass the `-Ddocs=true` option to the Meson build script. Generate and install the API reference documentation for `libproxy` using the Gtk-Doc tool and install it into the `/usr/share/gtk-doc/html/libproxy` directory.

This flag should normally be disabled.

### introspection
Pass the `-Dintrospection=true` option to the Meson build script. Generate and install the `Libproxy-1.0.gir` GIR metadata file to provide binding for the `libproxy` library to languages other than C using the GObject Introspection Framework.

It is safe to disable this flag.

### kde
Pass the `-Dconfig-kde=true` option to the Meson build script. Build the plugin to integrate with the KDE (K Desktop Environment) and read proxy settings from KDE system settings.

This flag should be enabled if the target system is running a KDE based desktop environment.

### test
Pass the `-Dtests=true` option to the Meson build script. Build the test suite provided with the source code. Execute the `meson test` command after the main build is completed to run tests and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.

### vala
Pass the `-Dvapi=true` option to the Meson build script. Generate and install the `libproxy-1.0.vapi` Vala language bindings for the `libproxy` library.

It is safe to disable this flag.
