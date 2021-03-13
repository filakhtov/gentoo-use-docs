# dev-cpp/cairomm

### doc
Pass the `-Dbuild-documentation=true` option to the meson build script. Use the Doxygen tool to generate documentation in the HTML format, including API documentation, data structures, namespaces and classes descriptions, class diagrams, etc.

It is safe to disable the flag.

### test
Pass the `-Dbuild-tests=true` option to the meson build script. Build the test suite provided with the source code and execute the `meson test` command to run the built tests after the main build is completed and check for any regressions.

This flag should normally be disabled, as it is primarily useful for the developers, maintainers and testers.
