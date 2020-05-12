# x11-libs/pango

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build command. Use the Gtk-Doc tool to generate documentation in the HTML format from source code annotations and install it into the system.

This flag should normally be disabled.

### introspection
Pass the `-Dintrospection=true` option to the meson build command. Generate and install the `Pango-1.0.gir`, `PangoCairo-1.0.gir`, `PangoFT2-1.0.gir` and, if the `X` flag is enabled, then `PangoXft-1.0.gir` GIR metadata files to provide dynamic bindings support for languages other than C using the GObject Introspection.

It is safe to disable this flag.

### test
Execute the `meson` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend a build time.

This flag should normally be disabled as it is mainly orinted towards developers, testers and maintainers.

### X
This flag is currently unused.
