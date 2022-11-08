# gnome-base/librsvg

### debug
Build the debug version of the `librsvg` library. When this flag is disabled, pass the `--release` flag to the `cargo build` command to produce production optimized version instead.

This flag should only be enabled if there is a need to debug the library itself or a linked binary.

### gtk-doc
Pass the `--enable-gtk-doc` option to the configure script. Use the Gtk-Doc tool to extract annotations from the source code to generate developer documentation in the HTML format and install it into the `/usr/share/gtk-doc/html/librsvg~` directory.

It is safe to disable this flag.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate GIR metadata `Rsvg-2.0.gir` file and generate a typelib from it during a build time to provide dynamic bindings support for languages other than C.

It is safe to disable this flag.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Generate the `librsvg-2.0.vapi` Vala bindings file during a build time using the GObject Introspection.

It is safe to disable this flag.
