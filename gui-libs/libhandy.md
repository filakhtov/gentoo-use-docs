# gui-libs/libhandy

### examples
Pass the `-Dexamples=true` option to the meson build command. Build and install the examples and demo applications, as well as their source code, including a python script that demonstrate the GObject introspection bindings usage and a demo C program with simple widgets.

This flag should normally be disabled.

### glade
Pass the `-Dglade_catalog=enabled` option to the meson build command. Install the `libhandy.xml` Glade catalog file to provide an ability to use the Handy's widgets in Glade UI designer.

It is safe to disable the flag.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build command. Use the Gtk-Doc to generate the API reference manual in the HTML format from the source code annotations and install it into the system. This documentation contains some notes on library compilation process and describes types and functions provided by the library.

This flag can be safely disabled, unless there is a need for developer documentation.

### introspection
Pass the `-Dintrospection=enabled` option to the meson build command. Generate and install the `Handy-0.0.gir` GIR metadata file to provide dynamic bindings for the `libhandy` library to languages other than C using the GObject introspection framework.

It is safe to disable this flag.

### test
Pass the `-Dtests=true` option to the meson build command. Start a new Xvfb session and execute the `meson test` command inside of it after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should be normally disabled, because it is primarily useful for the developers, maintainers and testers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `-Dvapi=true` option to the meson build command. Generate `libhandy-0.0.vapi` Vala language bindings for the libhandy library.

It is safe to disable this flag.
