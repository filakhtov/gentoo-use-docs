# gui-libs/gtksourceview

### gtk-doc
Pass the `-Dgtk_doc=true` option to the Meson build script. Use the Gtk-Doc tool to extract annotations from the source code to generate developer documentation in the HTML format and install it into the `/usr/share/gtk-doc/html/gtksourceview` directory.

This flag should normally be disabled.

### introspection
Pass the `-Dintrospection=enabled` option to the Meson build script. Generate and install the `GtkSource-4.gir` GIR metadata file to provide dynamic bindings for the `libgtksourceview-4` library to languages other than C using the GObject introspection framework.

This flag can be safely disabled.

### sysprof
Pass the `-Dsysprof=true` option to the Meson build script. Enable integration with sysprof profiler to capture and send various runtime metrics, such as timings of loading and parsing the source files.

This flag should only be enabled if there is a need to profile `libgtksourceview-4` based applications with Sysprof.

### test
Execute the `meson test` command inside of the virtual Xvfb session after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled because these tests are primarily useful for the developers, maintainers and testers.

### vala
Pass the `-Dvapi=true` option to the Meson build script. Generate the `gtksourceview-4.vapi` Vala language bindings for the `libgtksourceview-4` library.

It is safe to disable the flag.
