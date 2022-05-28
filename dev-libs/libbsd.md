# dev-libs/libbsd

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libbsd` library.

This flag should only ever be enabled if there is an explicit need for the static library.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
