# x11-libs/gtksourceview

### glade
Pass the `-Dglade_catalog=true` option to the meson build command. Generate and install the `gtksourceview.xml` Glade catalog file to provide an ability to use the `GtkSourceView` (GTK+ based source code viewer/highlighter) widgets in the Glade UI designer.

It is safe to disable the flag.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build command. Use the `Gtk-Doc` tool to generate and install library API reference in the HTML format for the `libgtksourceview` library using the source code annotations.

This flag can be safely disabled.

### introspection
Pass the `-Dgir=true` option to the meson build command. Generate and install the `GtkSource-3.0.gir` GIR metadata file to provide dynamic bindings for the `libgtksourceview` library to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### test
Start a new Xvfb session and execute the `meson test` command inside of it when the main build is completed to run the test suite provided with the source code and check for regression. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers or developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `-Dvapi=true` option to the meson build command. Generate the `gtksourceview-3.0.vapi` Vala bindings file for the `libgtksourceview` library.

It is safe to disable the flag.
