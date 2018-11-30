# media-libs/kvazaar

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libkvazaar` library.

This flag should only be enabled if there is a need for the static library.

### test
Execute the `make check` command when the main build is completed to run the test suite provided with the source code. This will extend the build time.

This flag should normally be disabled, because these tests are useful for the Gentoo team, developers and testers.
