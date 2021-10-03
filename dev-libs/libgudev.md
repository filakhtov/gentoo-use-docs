# dev-libs/libgudev

### introspection
Pass the `-Dintrospection=enabled` option to the Meson build script. Generate and install the `GUdev-1.0.gir` GIR metadata file to provide dynamic bindings support for the `libgudev` library to languages other than C.

It is safe to disable the flag.

### test
Pass the `-Dtests=enabled` option to the Meson build script. Build the test suite provided with the source code and run it after the main build is completed to check for any regressions. This will extend the build time.

This flag should normally be disabled as it is primarily oriented towards the developers, maintainers and testers.
