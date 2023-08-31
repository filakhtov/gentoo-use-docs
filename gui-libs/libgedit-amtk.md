# gui-libs/libgedit-amtk

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Use the Gtk-Doc tool to generate documentation from the source code annotations in the HTML format and install it into the `/usr/share/gtk-doc/html/` directory.

This flag should normally disabled, because documentation provided is tailored towards the developers utilizing the library, not end users.

### introspection
Pass the `-Dgobject_introspection=true` option to the meson build script. Generate and install the `Amtk-5.gir` GIR metadata file to provide bindings for the `libgedit-amtk` library for languages other than C using the GObject Introspection framework.

It is safe to disable this flag.
