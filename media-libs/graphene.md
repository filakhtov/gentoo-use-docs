# media-libs/graphene

### introspection
Pass the `-Dintrospection=enabled` (`disabled` if the flag is disabled) to the meson build script. Generate and install the `Graphene-1.0.gir` GIR metadata file to provide dynamic bindings for the `libgraphene` library to language other than C, using the GObject Introspection Framework.

This flag can be safely disabled.

### doc
Pass the `-Dgtk_doc=true` (`false` when the flag is disabled) to the meson build script. Use the Gtk-Doc tool to generate the API reference for the Graphene library and install it into the `/usr/share/gtk-doc/html/graphene` directory. Documentation is intended for developers who want to use this library and provides description of the different data structures and functions provided by the library.

It is safe to disable this flag.

### test
Pass the `-Dtests=true` (`false` when the flag is disabled) to the meson build script. Build the test suite provided with the source code, then run the `ninja test` command when the main build is completed to run tests and check for regressions.

This flag should normally be disabled, as it is mainly useful for maintainers, testers and developers.
