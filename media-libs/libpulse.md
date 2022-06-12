# media-libs/libpulse

### asyncns
Pass the `-Dasyncns=enabled` option to the meson build script. Use the `libasyncns` library for asynchronous name resolution when connecting to a network sink.

It is safe to disable the flag.

### dbus
Pass the `-Ddbus=enabled` option to the meson build script. Enable support for D-Bus protocol, e.g. to provide an ability to talk to RealtimeKit and change the process priority.

It is safe to disable the flag.

### doc
Pass the `-Ddoxygen=true` option to the meson build script. Use the Doxygen tool to generate an API documentation in an HTML format out of the source code and annotations and install it into the `/usr/share/doc/libpulse-<VERSION>` directory.

The flag can be safely disabled.

### glib
Pass the `-Dglib=enabled` option to the meson build script. Build and install the `libpulse-mainloop-glib` library that provides integration with the `libglib2` library to allow using PulseAudio client library in GLib-based programs.

This flag is recommended for regular desktop systems.

### gtk
Pass the `-Dgtk=enabled` option to the meson build script. Enable integration with the GTK+3 toolkit. Provide an ability to obtain application icon and X11 display the client application belongs to.

It is safe to disable this flag.

### selinux
Pull in the [sec-policy/selinux-pulseaudio](../sec-policy/selinux-pulseaudio.md) package as a dependency. Install SELinux policies to allow PulseAudio to properly run under a SELinux-restricted kernel.

This flag should only ever be toggle system-wide, i.e. as part of the SELinux-enabled portage profile.

### systemd
Pass the `-Dsystemd=enabled` option to the meson build script. Enable integration with systemd, e.g. provide support for socket activation and enable logging via the SystemD journal.

This flag should be enabled on the systems that use the SystemD init daemon.

### tcpd
Pass the `-Dtcpwrap=enabled` option to the meson build script. Enable support for the TCP wrappers (aka `tcpd`) tool to provide fine-grained control over network connections established to the PulseAudio server via an ACL system.

This flag should normally be disabled as TCP wrappers is obsolete and unmaintained.

### test
Pass the `-Dtests=true` option to the meson build script. Build the test suite provided with the source code and execute the `meson test` command after the main build is completed to run it and check for any regressions. This will extend the build time.

This flag should normally be disabled as these tests are mainly useful for developers, testers and maintainers.

### valgrind
Pass the `-Dvalgrind=enabled` option to the meson build script. Enable additional macroses in the code that provide proper support and fix some incorrect reporting when running applications linked against the `libpulse` library using Valgrind.

This flag should only be enabled if there is a need to debug applications with Valgrind.

### X
Pass the `-Dx11=enabled` option to the meson build script. Enable support for X11 Windowing system. Build and install the `pax11publish` utility that can be used to dump or manipulate the PulseAudio server credentials that can be stored as properties on the X11 root window.

This flag should only be enabled if the target system runs the X Server.
