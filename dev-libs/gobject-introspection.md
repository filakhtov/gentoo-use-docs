# dev-libs/gobject-introspection

### doctool
Pass the `-Ddoctool=enabled` option to the meson build command. Build and install a `g-ir-doc-tool` tool for generating documentation from comments and annotations in the source code.

It is safe to disable the flag.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build command. Use the `Gtk-Doc` tool to generate and install the `libgirepository` library API reference in the HTML format.

The flag can be safely disabled.

### test
Pass the `-Dcairo=enabled` option to the meson build command. Execute the `meson test` command after the main build is completed. Run a test suite provided with the source code to check for regressions. This will extend the build time.

This flag should normally be disabled as it is only useful for maintainers, testers and developers.
