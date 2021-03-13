# dev-cpp/gtkmm

### aqua
Make sure that [x11-libs/gtk+](../x11-libs/gtk+.md) package has the `aqua` flag enabled. Provide an ability to use the Quartz GDK backend (see `aqua` flag on the [x11-libs/gtk+](../x11-libs/gtk+.md) package for additional details).

This flag only makes sense on macOS and should be disabled otherwise.

### doc
Pass the `-Dbuild-documentation=true` option to the meson build script. Use the Doxygen tool to generate an API documentation in the HTML format, that describes library components, including modules, namespaces, classes, provides class relationship diagrams, etc, and install it into the `/usr/share/doc/gtkmm-<VERSION>` directory.

It is safe to disable the flag.

### test
Pass the `-Dbuild-tests=true` option to the meson build script. Start a new Xvfb session and execute the `meson test` command inside of it when the main build is completed to run the built regression test suite that is provided the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.

### wayland
Make sure that [x11-libs/gtk+](../x11-libs/gtk+.md) package has the `wayland` flag enabled. Provide an ability to use Wayland GDK backend (see `wayland` flag on the [x11-libs/gtk+](../x11-libs/gtk+.md) package for additional details).

This flag should be enabled if there is a need to run `libgtkmm` apps under the Wayland window server.

### X
Make sure that [x11-libs/gtk+](../x11-libs/gtk+.md) package has the `X` flag enabled. Pass the `-Dbuild-x11-api=true` option to the meson build script. Provide an ability to use X11 GDK backend (see `X` flag on the [x11-libs/gtk+](../x11-libs/gtk+.md) package for additional details).

This flag should be enabled if there is a need to run `libgtkmm` apps under the X window server.
