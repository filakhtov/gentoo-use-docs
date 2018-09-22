# gnome-base/libgnome-keyring

### introspection
Generate and install the `GnomeKeyring-1.0.gir` GIR metadata file to provide dynamic bindings for the `libgnome-keyring` library to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### debug
Pass the `--enable-debug=yes` option to the configure script. Disable all compiler optimizations and produce the library with debugging symbols and make it produce additional runtime debugging output.

This flag should only be enabled for debugging purposes.

### test
Start a session D-Bus instance using the `dbus-launch` command and execut the `make check` command inside of it after the main build is completed. Run the test suite provided with the source code. This will extend a build time.

This flag should be disabled as it is primarily oriented towards the Gentoo team, testers and developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Generate and install the `gnome-keyring-1.vapi` Vala language bindings for the `libgnome-keyring` library.

It is safe to disable the flag.
