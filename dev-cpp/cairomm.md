# dev-cpp/cairomm

### gtk-doc
Pass the `-Dbuild-documentation=true` option to the meson build script. Use the Doxygen tool to generate documentation in the HTML format, including API documentation, data structures, namespaces and classes descriptions, class diagrams, etc.

It is safe to disable the flag.

### test
Pass the `-Dbuild-tests=true` option to the meson build script. Build the test suite provided with the source code and execute the `meson test` command to run the built tests after the main build is completed and check for any regressions.

This flag should normally be disabled, as it is primarily useful for the developers, maintainers and testers.

### X
Ensure that the `X` flag on the [x11-libs/cairo](../x11-libs/cairo.md) dependency is in sync with this package, that is it's either enabled or disabled for both of the packages.

It is safe to disable this flag if there is no need to use Cairo in the X Window System environment.
