# gui-libs/amtk

### gtk-doc
Pass the `-Dgtk_doc=true` option to the Meson build script. Use the GTK-Doc tool to generate reference manual in the HTML format and install it into the `/usr/share/gtk-doc/html/amtk-<version>` directory.

It is safe to disable this flag.

### introspection
Pass the `-Dgobject_introspection=true` option to the Meson build script. Generate and install the `Amtk-5.gir` GIR metadata file to provide dynamic bindings for the `libamtk` library to languages other than C using the GObject introspection framework.

This flag can be safely disabled.
