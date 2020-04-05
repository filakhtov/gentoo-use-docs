# dev-libs/libinput

### doc
Pass the `-Ddocumentation=true` option to the Meson build script. Generate additional documentation in the HTML format using the Doxygen and Graphviz tools and install it into the `/usr/share/doc/libinput-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Pass the `-Dtest=true` option to the Meson build script. Build the test suite provided with the source code and run it using the `meson test` command after the main build is completed to check for regressions. This will extend the build time.

This flag should normally be disabled, because it is primarily oriented towards developers, testers and maintainers, instead of end users.
