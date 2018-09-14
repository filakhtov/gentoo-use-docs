# dev-libs/libinput

### doc
Pass the `-Ddocumentation=true` option to the Meson build script. Generate additional documentation in the HTML format using the Doxygen and Graphviz tools and install it into the `/usr/share/doc/libinput-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Pass the `-Dtests=true` option to the Meson build script. Execute the `ninja test` command after the main build is completed to run the test suite provided with the source code. This will extend a build time.

This flag should normally be disabled because these tests are primarily oriented towards testers or developers.
