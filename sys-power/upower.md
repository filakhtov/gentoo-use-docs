# sys-power/upower

### doc
Pass a `--enable-gtk-doc` option to a configure script. Use a Gtk-Doc tool to generate developer documentation out of the source code and annotations.

It is safe to disable the flag.

### introspection
Pass a `--enable-instrospection` option to a configure script. Generate and install a `UPowerGlib-1.0.gir` GIR metadata file to provide dynamic bindings for a `libupower-glib` library to languages other than C by using a GObject Introspection infrastructure.

The flag can be safely disabled.

### ios
Pass a `--with-idevice` option to a configure script. Use a `libimobiledevice` library to recognize and properly handle Apple iOS based devices when connected over USB.

This flag should be enabled if there ever is a need to connect an iOS based device.

### selinux
Pull in a [sec-policy/selinux-devicekit](../sec-policy/selinux-devicekit.md) package as a dependency that provides SELinux policies necessary for a `upowerd` daemon to properly run under a SELinux-restricted kernel.

This flag should only ever be toggled system-wide, i.e. as part of a SELinux-enabled Portage profile.
