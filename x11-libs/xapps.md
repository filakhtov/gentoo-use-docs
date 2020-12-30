# x11-libs/xapps

### gtk-doc
Pass the `-Ddocs=true` option to the meson build script. Use the Gtk-Doc tool to generate reference API documentation from the source code annotations and install it into the system.

This flag can be safely disabled.

### introspection
Ensure that the `introspection` flag is enable for the [x11-libs/gdk-pixbuf](../x11-libs/gdk-pixbuf.md) and [x11-libs/gtk+](../x11-libs/gtk+.md) packages. These dependencies are required to generate the `XApp-1.0.gir` GIR metadata file to provide dynamic bindings for a `libxapp` library to languages other than C using a GObject Introspection framework.

This flag should be enabled.

### static-libs
This flag does nothing and should be disabled.
