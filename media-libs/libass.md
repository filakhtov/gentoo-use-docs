# media-libs/libass

### fontconfig
Pass the `--enable-fontconfig` option to the configure script. Use the `libfontconfig` library so that system font configuration and preferences are applied when rendering subtitles.

It is safe to disable this flag.

### test
Pass the `--enable-test` option to the configure script. Build the test suite provided with the source code and execute the `make check` command after the main build is completed to run it and check for any regressions. This will extend the build time.

This flag should normally be disabled because these tests are primarily oriented towards the developers, maintainers and testers.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
