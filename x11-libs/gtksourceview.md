# x11-libs/gtksourceview

### glade
Pass the `--enable-glade-catalog` option to the configure script. Generate and install the `gtksourceview.xml` Glade catalog file to provide an ability to use the GtkSourceView widgets in Glade UI designer.

It is safe to disable the flag.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `GtkSource-3.0.gir` GIR metadata file to provide dynamic bindings for the `libgtksourceview` library to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed to run the test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers or developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Generate the `gtksourceview-3.0.vapi` Vala bindings file for the `libgtksourceview` library.

It is safe to disable the flag.
