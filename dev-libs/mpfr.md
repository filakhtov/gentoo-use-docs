# dev-libs/mpfr

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libmpfr` library. When disabled, remove all statically linked files produced during a compilation before installing the package.

This flag should only ever be enabled if there is an explicit need for the static library.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
