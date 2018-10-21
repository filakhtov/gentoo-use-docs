# dev-libs/libsigc++

### doc
Pass the `--enable-documentation` option to the configure script. Generate documentation in the HTML format using the Doxygen tool, including API documentation, description of modules, classes, functions, class relationship diagrams, etc, and install it into the `/usr/share/doc/libsigc++-2.0` directory. Also install additional example C++ source code showing how to use the library into the `examples` subdirectory of the same directory.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libsigc-2.0` library.

This flag should be only enabled if there is an explicit need for the static library.

### test
Pass the `--enable-benchmark` option to the configure script. Build benchmarking tests that check performance of the signal processing. Execute the `make check` command after the main build is completed. Run the regression test suite provided with the source code. This will extend the build time. When disabled, patch the `Makefile.am` and `Makefile.in` files to skip building test tools.

This flag should normally be disabled, because it is mainly useful for the Gentoo team, testers and developers.
