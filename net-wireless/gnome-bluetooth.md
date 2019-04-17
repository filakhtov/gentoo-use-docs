# net-wireless/gnome-bluetooth

### gtk-doc
Pass the `-Dgtk_doc=true` (`false` when the flag is disabled) optiont to the meson build script. Use the Gtk-Doc tool to generate documentation, describing the API reference and object hierarchy in the HTML format and install it into the `/usr/share/gtk-doc/html/gnome-bluetooth` directory.

This flag can be safely disabled.

### introspection
Pass the `-Dintrospection=true` (`false` if the flag is disabled) option to the meson build script. Generate and install the `GnomeBluetooth-1.0.gir` GIR metadata file to provide dynamic bindings for the `libgnome-bluetooth` library to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.
