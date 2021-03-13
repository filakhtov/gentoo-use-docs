# dev-libs/json-glib

### gtk-doc
Pass the `-Ddocs=enabled` (`disabled` when disabled) option to the meson build command. Generate documentation using the GTK-Doc tool in the HTML format and install it into the `/usr/share/gtk-doc/html/json-glib-<VERSION>/` directory, including overview of the library, developer reference manual, description of parsing, reading, writing and generating JSON streams, etc.

This flag can be safely disabled.

### introspection
Pass a `-Dintrospection=enabled` (`disabled` when disabled) option to the meson build command. Generate and install a `Json-1.0.gir` GIR metadata file to provide dynamic bindings for a `libjson-glib` library to languages other than C using a GObject Introspection infrastructure.

It is safe to disable the flag.
