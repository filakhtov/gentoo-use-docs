# dev-libs/libxmlb

### doc
Pass the `-Dgtkdoc=true` option to the Meson build script. Use the GTK-Doc tool to generate documentation from the source code annotations in the HTML format and install it into the `/usr/share/gtk-doc/html/libxmlb-<version>` directory.

It is safe to disable this flag.

### introspection
Pass the `-Dintrospection=true` option to the Meson build script. Generate and install the `Xmlb-2.0.gir` GIR Metadata file to provide dynamic bindings for the `libxmlb` library to languages other than C using the GObject Introspection framework.

This flag can be safely disabled.

### stemmer
Pass the `-Dstemmer=true` option to the Meson build script. Link against the `libstemmer` library to provide an ability to stem words and perform more efficient memory mapping of the text data in the XML file.

It is safe to disable this flag.

### test
Pass the `-Dtests=true` option to the Meson build script. Build the test suite provided with the source code and execute the `meson test` command to run it after the main build is completed and check for any regression.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
