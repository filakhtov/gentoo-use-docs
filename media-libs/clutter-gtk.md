# media-libs/clutter-gtk

### debug
Pass the `--enable-debug=yes` option to the configure script. Build the `libclutter-gtk` library with debugging symbols included.

This flag should only be enabled for debugging purposes.

### examples
Install additional example C source code into the `/usr/share/doc/clutter-gtk-<VERSION>/examples` directory. Example programs include multiple clutter stages embedded into the single window, event handling, using GTK widgets as clutter actors, etc.

It is safe to disable the flag.

### gtk
Ensure that the [media-libs/clutter](../media-libs/clutter.md) package has the `gtk` flag synchronized with this package's flag (see `gtk` flag for the `clutter` package).

This flag should be enabled if there is a need to use the GDK clutter backend.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `GtkClutter-1.0.gir` GIR metadata file to provide bindings for the `libclutter-gtk` library to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### wayland
Ensure that both the [x11-libs/gtk+](../x11-libs/gtk+.md) and the [media-libs/clutter](../media-libs/clutter.md) packages has the `wayland` flag synchronized with this package's flag (see `wayland` flag for the `gtk+` and the `clutter` packages).

This flag should be enabled if there is a need to run Wayland server.

### X
Ensure that both the [x11-libs/gtk+](../x11-libs/gtk+.md) and the [media-libs/clutter](../media-libs/clutter.md) packages has the `X` flag synchronized with this package's flag (see `X` flag for the `gtk+` and the `clutter` packages).

This flag should normally be enabled, unless there is a need to run clutter outside of X server.
