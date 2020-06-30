# dev-lang/orc

### gtk-doc
Pass the `-Dgtk_doc=enabled` option to the meson build script. Use the Gtk-Doc tool to generate documentation in the HTML format and install it into the `/usr/share/gtk-doc/html/orc` directory. This is developer centric documentation, explaining how to build the library, describing its API and how to use it for building applications.

It is safe to disable this flag.

### static-libs
Pass the `-Ddefault_library=both` (or `shared` if the flag is disabled) option to the meson build script. Build and install a statically linked version of the `liborc` library.

This flag should normally be disabled, unless there is an explicit need for the static library.

### test
Pass the `-Dtests=enabled` option to the configure script. Build the test suite provided with the source code and run it using the `meson test` command after the main build is completed to check for regressions. This will extend the build time.

The flag should normally be disabled, because these tests are mainly used by the maintainers, developers and testers, not the end users.
