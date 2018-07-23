# dev-libs/libpipeline

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libpipeline` library.

This flag should only be enabled if there is a need for the static library.

### test
Execute a `make check` command once the main build is completed. Run a test suite provided with the source code.

The flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
