# gui-libs/tepl

### gtk-doc
Pass the `-Dgtk_doc=true` option to the Meson build script. Use the Gtk-Doc tool to generate the API reference documentation, list of exported symbols and some library usage examples.

It is safe to disable this flag.

### test
Start a new Xvfb session and execute the `meson test` command inside of it after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because it is primarily intended for the developers, maintainers and testers.
