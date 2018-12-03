# dev-libs/appstream-glib

### doc
Pass the `-Dgtk-doc=true` option to the meson build command. Use the GTK-Doc tool to generate developer documentation in the HTML format and install it into the `/usr/share/gtk-doc/html/appstream-glib-<VERSION>` directory.

It is safe to disable the flag.

### introspection
Pass the `-Dintrospection=true` option to the meson build command. Generate and install the `AppStreamGlib-1.0.gir` and the `AppStreamBuilder-1.0.gir` GIR metadata files to provide bindings for the `libappstream-glib` and the `libappstream-builder` libraries to languages other than C using the GObject Introspection framework.

This flag can be safely disabled.

### stemmer
Pass the `-Dstemmer=true` option to the meson build command. Link against the `libstemmer` (Snowball string processing language implementation) library to provide for higher-quality searching through AppStream metadata that is available by deriving a stemmed version of the search token.

It is safe to disable the flag.
