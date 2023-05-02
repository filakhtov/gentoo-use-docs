# media-libs/gsound

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Generate the API reference documentation for the `libgsound` library from the source code using the Gtk-Doc tool and install it into the system.

This flag can be safely disabled.

### introspection
Pass the `-Dintrospection=true` option to the meson build script. Generate and install the `GSound-1.0.gir` GIR metadata file and associated typelib to provide dynamic bindings for the `libgsound` library to languages other than C using the GOject Introspection framework.

It is safe to disable this flag.

### vala
Pass the `-Denable_vala=true` option to the meson build script. Generate and install the `gsound.vapi` Vala bindings file to provide Vala bindings for the `libgsound` library.

This flag can be safely disabled.
