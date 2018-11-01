# dev-libs/libical

### doc
This flag does nothing and should be disabled.

### examples
Install additional example files into the `/usr/share/doc/libical-<VERSION>/examples` directory. Examples comprise of C source code that demonstrates how to use library for a number of different use cases.

It is safe to disable the flag.

### static-libs
Build and install a statically linked version of the `libical`, `libical_cxx`, `libicalss`, `libicalss_cxx`, `libicalvcal` libraries. When disabled, pass the `-DSHARED_ONLY=ON` option to the cmake command to skip building static libraries.

This flag should only ever be enabled if there is an explicit need for the static libraries.
