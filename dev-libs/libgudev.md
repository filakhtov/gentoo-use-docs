# dev-libs/libgudev

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `GUdev-1.0.gir` GIR metadata file to provide dynamic bindings support for the `libgudev` library to languages other than C.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libgudev` library.

This flag should only be enabled if there is an explicit need for the static library.
