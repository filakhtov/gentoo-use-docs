# dev-libs/libtasn1

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libtasn1` library.

This flag should only be enabled when the static library is required.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code. This will extend the build time.

This flag should normally be disabled as it is primarily oriented towards testers and developers and is used by the Gentoo team.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
