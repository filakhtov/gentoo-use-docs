# dev-util/gtk-doc

### emacs
Compile and install the `gtk-doc.el` Emacs file to provide an ability to quickly pull up or update documentation header for functions.

It is safe to disable this flag.

### test
Pass the `-Dtests=true` option to the meson build script. Build and execute the test suite provided with the source code after the main build is completed and check for any regressions. This will extend the build time.

This flag should normally be disabled, because the these tests are primarily useful for the developers, maintainers and testers.
