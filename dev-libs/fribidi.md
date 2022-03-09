# dev-libs/fribidi

### doc
Pass the `-Ddocs=true` option to the meson build script. Generate documentation using the `c2man` tool that extracts comments from C source
code and generates functional interface documentation in the same format as sections 2 & 3 of the Unix Programmer's Manual.

It is safe to disable this flag.

### test
Pass the `-Dtests=true` option to the meson build script. Execute the `meson test` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, as it is primarily oriented towards the developers, maintainers and testers.
