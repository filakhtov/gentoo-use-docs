# gnome-extra/cinnamon-menus

### debug
Pass a `--enable-debug=yes` option to a configure script. Define a `G_ENABLE_DEBUG` macro to enable support for runtime checking to print out different
types of debugging information when running.

This flag should only be enabled for debugging purposes.

### introspection
Pass a `--enable-introspection` option to a configure script. Generate and install a `CMenu-3.0.gir` GIR metadata file to provide dynamic bindings for a `libcinnamon-menu-3` library to languages other than C using a GObject Introspection infrastructure.

It is safe to disable the flag.
