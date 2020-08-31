# gui-libs/tepl

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `Tepl-4.gir` GIR metadata file to provide dynamic bindings for the `libtepl` library to languages other than C using the GObject introspection framework.

It is safe to disable this flag.

### test
Start a new Xvfb session and execute the `make check` command inside of it after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because it is primarily intended for the developers, maintainers and testers.
