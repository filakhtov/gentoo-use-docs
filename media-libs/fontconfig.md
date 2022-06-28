# media-libs/fontconfig

### doc
Pass the `--enable-docbook` option to the configure script. Generate documentation from a source code instead of installing a prebuilt one.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libfontconfig` library.

This flag should only be enabled if there is a need for the static library.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
