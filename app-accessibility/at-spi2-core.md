# app-accessibility/at-spi2-core

### dbus-broker
Pass the `-Ddefault_bus=dbus-broker` (instead of `dbus-daemon`) option to the meson build script. Use the [`dbus-broker` implementation](https://github.com/bus1/dbus-broker/wiki) instead of the default D-Bus daemon.

It is safe to disable this flag.

### gtk-doc
Pass the `-Ddocs=true` (`false` if the flag is disabled) option to the meson build script. Use the Gtk-Doc tool to extract annotations from the source code to generate developer documentation in the HTML format and install it into the `/usr/share/gtk-doc/html/at-spi2-core` directory.

This flag should normally be disabled.

### introspection
Pass the `-Dintrospection=enabled` (`disabled` when the flag is disabled) option to the meson build command. Generate GIR metadata `Atspi-2.0.gir` file during a build time to provide dynamic bindings support for languages other than C.

It is safe to disable the flag.

### systemd
Pass the `-Duse_systemd=true` option to the meson build script. Enable support for running under the systemd init system.

This flag should only be enabled system-wide on the systems that use systemd.

### test
Start a new Xvfb session with D-Bus and execute the `meson test` command inside of it when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend a build time.

This flag should normally be disabled, as it is primarily used by the package developers and maintainers.

### X
Pass the `-Dx11=enabled` (`disabled` if the flag is disabled) option to the meson build command. Provide support for X-specific device event controller support.

This flag should be enabled if there is a need for accessibility support for X.Org display server.
