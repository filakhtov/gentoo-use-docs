# dev-libs/nettle

### asm
Pass the `--enable-assembler` option to the configure script. Enable low level highly optimized hardware-specific assembly optimizations for variety of cryptographic algorithms.

This flag should normally be enabled for performance improvements.

### doc
Pass the `--enable-documentation` option to the configure script. Generate and install additional documentation in the HTML and PDF formats into the `/usr/share/doc/nettle-<VERSION>` directory.

It is safe to disable the flag.

### gmp
Pass the `--enable-public-key` option to the configure script. Build and install the `libhogweed` library to provide support for public key algorithms (for encryption and signature verification) that depends on the `GnuMP` library for bignum math operations.

This flag should be enabled if there is a need for public key algorithms in libnettle.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libnettle` library (and the `libhogweed` library if `gmp` flag is enabled).

The flag should only be enabled if the static libraries are required.

### test
Execute the `make check` command after the main build is completed. Run a test suite provided with the source code. This will extend a build time. When disabled, patch the `Makefile.in` file to exclude the `testsuite` and `examples` directories from being built to shrink the build time.

This flag should normally be disabled as it is mainly used by the Gentoo team, testers and developers.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
