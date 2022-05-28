# gui-libs/libadwaita

### introspection
Pass the `-Dintrospection=enabled` option to the Meson build script. Generate and install the `Adw-1.gir` GIR metadata file to provide dynamic bindings for the `libadwaita` library to languages other than C using the GObject Introspection framework.

This flag can be safely disabled.

### test
Pass the `-Dtests=true` option to the Meson build script to build the test suite and execute the `meson test` command inside of the virtual Xvfb session to run the test suite provided with the source code and check for any regressions.

This flag should normally be disabled because these tests are primarily oriented towards the developers, maintainers and testers.

### vala
repare environment for the configure script to find an appropriate version of vala files. Pass the `-Dvapi=true` option to the configure script. Generate the `libadwaita-1.vapi` Vala language bindings for the `libadwaita` library.

It is safe to disable this flag.
