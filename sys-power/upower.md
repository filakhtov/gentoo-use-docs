# sys-power/upower

### doc
Pass the `-Dgtk-doc=true` option to the Meson build script. Use a Gtk-Doc tool to generate developer documentation out of the source code and annotations.

It is safe to disable the flag.

### introspection
Pass the `-Dinstrospection=enabled` option to the Meson build script. Generate and install a `UPowerGlib-1.0.gir` GIR metadata file to provide dynamic bindings for a `libupower-glib` library to languages other than C by using a GObject Introspection infrastructure.

The flag can be safely disabled.

### ios
Pass a `-Didevice=enabled` option to the Meson build script. Use a `libimobiledevice` library to recognize and properly handle Apple iOS based devices when connected over USB.

This flag should be enabled if there ever is a need to connect an iOS based device.

### selinux
Pull in a [sec-policy/selinux-devicekit](../sec-policy/selinux-devicekit.md) package as a dependency that provides SELinux policies necessary for a `upowerd` daemon to properly run under a SELinux-restricted kernel.

This flag should only ever be toggled system-wide, i.e. as part of a SELinux-enabled Portage profile.

### test
Execute the `meson test` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are mainly oriented towards the maintainers, developers and testers.
