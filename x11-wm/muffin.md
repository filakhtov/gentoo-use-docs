# x11-wm/muffin

### introspection
Pass the `-Dintrospection=true` option to the meson build script. Generate and install a `CoglPango-0`, `Clutter-0`, `Cally-0`, `Meta-0`, `Cogl-0` and `ClutterX11-0` GIR metadata files to provide dynamic bindings for the `libmuffin-clutter`, `libmuffin-cogl`, `libmuffin-cogl-pango` and `libmuffin` libraries to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### sceencast
Pass the `-Dremote_desktop=true` option to the meson build script. Enable remote desktop and screen cast support. This is implemented in GNOME Mutter and most likely doesn't properly work in Cinnamon's fork.

This flag should normally be disabled.

### sysprof
Pass the `-Dprofiler=true` option to the meson build script. Enable better integration with Sysprof 3. Enable traces that capture data about time spent in various routines and expose it to the profiler.

This flag should normally be disabled.

### test
Pass the `-Dtests=true`, `-Dcogl_tests=true` and `-Dclutter_tests=true` options to the meson build script. Build the test suite provided with the source code. Start a new Xvfb session and execute the `meson test` command after the main build is complete to run the suite and check for any regressions. This will extend the build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.

### udev
Pass the `-Dudev=true` option to the meson build script. Enable udev support for the X11 backend, allowing to detect various device capabilities, such as trackball or trackpoint.

It is recommended to enable this flag to provide support for advanced device capabilities.
