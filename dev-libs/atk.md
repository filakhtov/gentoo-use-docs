# dev-libs/atk

### gtk-doc
Pass the `-Ddocs=true` (`false` when the flag is disabled) option to the meson build command. Use the Gtk-Doc tool to extract annotations from the source code to generate developer documentation in the HTML format and install it into the `/usr/share/gtk-doc/html/atk` directory.

This flag should normally be disabled.

### introspection
Pass the `-Dintrospection=true` (`false` if the flag is disabled) option to the meson build command. Generate the `Atk-1.0.gir` GIR metadata file and compile a typelib from it during a build time to provide dynamic bindings support for languages other than C.

This flag can be safely disabled.
