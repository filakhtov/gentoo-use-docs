# dev-cpp/cairomm

### aqua
Make sure that the `aqua` flag is enabled for the [x11-libs/cairo](../x11-libs/cairo.md) package.

This flag should be disabled as it is only useful on the macOS.

### doc
Pass the `--enable-documentation` option to the configure script. Use the Doxygen tool to generate documentation in the HTML format, including API documentation, data structures, namespaces and classes descriptions, class diagrams, etc.

It is safe to disable the flag.

### svg
Make sure that the `X` flag is enabled for the [x11-libs/cairo](../x11-libs/cairo.md) package (see `cairo` package description for details) to enable support for the SVG (Scalable Vector Graphics) image format.

This flag should be in sync with the `cairo`s flag.

### X
Make sure that the `X` flag is enabled for the [x11-libs/cairo](../x11-libs/cairo.md) package (see `cairo` package description for details).

This flag should be in sync with the `cairo`s flag.
