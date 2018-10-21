# dev-cpp/gtkmm

### aqua
Make sure that [x11-libs/gtk+](../x11-libs/gtk+.md) package has the `aqua` flag enabled. Pass the `--enable-quartz-backend` option to the configure script. Provide an ability to use the Quartz GDK backend (see `aqua` flag on the [x11-libs/gtk+](../x11-libs/gtk+.md) package for additional details).

This flag only makes sense on macOS and should be disabled otherwise.

### doc
Pass the `--enable-documentation` option to the configure script. Use the Doxygen tool to generate an API documentation in the HTML format, that describes library components, including modules, namespaces, classes, provides class relationship diagrams, etc, and install it into the `/usr/share/doc/gtkmm-<VERSION>` directory.

It is safe to disable the flag.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run the regression test suite provided with the source code. This will extend an overall build time. When disabled, patch the `Makefile.in` and `Makefile.am` files to skip building test code.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers or developers.

### wayland
Make sure that [x11-libs/gtk+](../x11-libs/gtk+.md) package has the `wayland` flag enabled. Pass the `--enable-wayland-backend` option to the configure script. Provide an ability to use Wayland GDK backend (see `wayland` flag on the [x11-libs/gtk+](../x11-libs/gtk+.md) package for additional details).

This flag should be enabled if there is a need to run `libgtkmm` apps under the Wayland window server.

### X
Make sure that [x11-libs/gtk+](../x11-libs/gtk+.md) package has the `X` flag enabled. Pass the `--enable-x11-backend` option to the configure script. Provide an ability to use X11 GDK backend (see `X` flag on the [x11-libs/gtk+](../x11-libs/gtk+.md) package for additional details).

This flag should be enabled if there is a need to run `libgtkmm` apps under the X window server.
