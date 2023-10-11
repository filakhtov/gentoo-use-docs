# dev-libs/sord

### doc
Pass the `-Ddocs=enabled` option to the meson build script. Use the Doxygen tool to generate and install documentation in the HTML format. This documentation includes library API reference, describing various provided types and functions.

This flag should normally be disabled, as this documentation is tailored for developers, not end users.

### test
Pass the `-Dtests=enabled` option to the meson build script. Build the test suite provided with the source code and execute `meson test` command after the build is completed to run the tests and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.

### tools
Pass the `-Dtools=enabled` option to the meson build script. Build and install command-line utilities: `sordi` - to load RDF data into a model and write it back out; and `sord_validate` - a simple validator for RDF.
