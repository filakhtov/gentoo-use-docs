# media-libs/libvorbis

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libvorbis`, `libvorbisenc` and the `libvorbisfile` libraries.

This flag should only be enabled if there is a need for the static libraries.

### test
Pass the `--enable-oggtest` option to the configure script. Execute the `make check` command when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the overall build time.

This flag should normally be disabled, because these tests are primarily oriented towards maintainers, developers and testers.
