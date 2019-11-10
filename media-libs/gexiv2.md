# media-libs/gexiv2

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build command. Use the GTK-Doc tool to generate C API reference documentation for the GExiv2 library using the annotations provided in the source code and install it into the `/usr/share/gtk-doc` directory.

It is safe to disable the flag.

### introspection
Pass the `-Dintrospection=false` option to the meson build command. Generate the GIR metadata `GExiv2-0.10.gir` file during a build time to provide dynamic bindings for the Exiv2 library for languages other than C using the GObject introspection framework.

This flag can be safely disabled.

### python
Requires an `introspection` flag to be enabled. For every active Python implementation install the `GExiv2` Python module that uses the GObject wrapper around the Exiv2 library to provide Python bindings.

It is safe to disable this flag.

### static-libs
This flag does nothing and should be disabled.

### test
Run the `meson test` command when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards developers, maintainers and testers.

### vala
Requires an `introspection` flag to be enabled. Pass the `-Dvapi=true` option to the meson build script. Generate and install the `gexiv2.vapi` Vala bindings that provide access to the Exiv2 library using the GObject wrapper. Install the `gexiv2-dump.vala` tool which is written in Vala and simply dumps metadata for a given file to the standard output.

This flag can be safely disabled.
