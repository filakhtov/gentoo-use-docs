# dev-libs/libdaemon

### doc
Run the `make doxygen` command during the build to generate the API documentation from the source code annotation in the HTML format using the Doxygen tool and install it into the `/usr/share/doc/libdaemon-<version>/html` directory.

It is safe to disable the flag.

### examples
Install the `testd.c` source file from the `examples` subdirectory of the source tree into the `/usr/share/doc/libdaemon-<version>/examples` documentation directory. This example demonstrates how to use the library to build a simple daemon (a forking program), properly handle various signals, manage file descriptors and so on.

This flag can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libdaemon` library.

This flag should only be enabled if there is an explicit need for the static library.
