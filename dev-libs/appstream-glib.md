# dev-libs/appstream-glib

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `AppStreamGlib-1.0.gir` and the `AppStreamBuilder-1.0.gir` GIR metadata files to provide bindings for the `libappstream-glib` and the `libappstream-builder` libraries to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to provide an ability to translate programs messages into various languages at runtime based on the system locale settings.

This flag should be enabled if there is a need to use appstream tools in languages other than English.

### stemmer
Pass the `--enable-stemmer` option to the configure script. Link against the `libstemmer` (Snowball string processing language implementation) library to provide for higher-quality searching through AppStream metadata that is available by deriving a stemmed version of the search token.

It is safe to disable the flag.
