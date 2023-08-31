# gui-libs/libgedit-gtksourceview

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Use the Gtk-Doc tool to generate API documentation from the source code in the HTML format and install it into the `/usr/share/gtk-doc/html/libgedit-gtksourceview` directory.

This flag can be safely disabled, as this documentation is only useful for developers using the `libgedit-gtksourceview` library to develop against, not the end users.

### test
Start a new D-Bus session inside of the virtual Xvfb session and execute the `meson tests` command inside of it to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
