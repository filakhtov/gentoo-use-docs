# x11-libs/libnotify

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Use the Gtk-Doc tool to generate the libnotify API reference manual in the HTML format and install it into the `/usr/share/gtk-doc` directory.

This flag can be safely disabled.

### introspection
Pass a `-Dintrospection=enabled` option to the meson build script. Generate and install a `Notify-0.7.gir` GIR metadata file to provide dynamic bindings for a `libnotify` library to languages other than C using a GObject Introspection infrastructure.

It is safe to disable the flag.

### test
Pass a `-Dtests=true` option to the meson build script. Build test code during the main build process and execute the `meson test` command once it is completed to run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is mainly used by the maintainers, testers or developers.
