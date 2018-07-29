# dev-libs/libtasn1

### doc
Install additional documentation files in the PDF and HTML formats into the `/usr/share/doc/libtasn1-<VERSION>` directory.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libtasn1` library.

This flag should only be enabled when the static library is required.

### valgrind
Pass the `--enable-valgrind-tests` option to the configure script. Use the Valgrind tool when running a test suite.

This flag should be disabled because tests are never executed for this package.
