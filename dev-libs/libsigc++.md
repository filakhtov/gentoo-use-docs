# dev-libs/libsigc++

### gtk-doc
Pass the `-Dbuild-documentation=true` option to the meson build script. Generate documentation in the HTML format using the Doxygen tool, including API documentation, description of modules, classes, functions, class relationship diagrams, etc, and install it into the `/usr/share/doc/libsigc++-2.0` directory. Also install additional example C++ source code showing how to use the library into the `examples` subdirectory of the same directory.

It is safe to disable the flag.

### test
Pass the `-Dbenchmark=true` option to the meson build script. Build benchmarking tests that check performance of the signal processing. Execute the `meson test` command after the main build is completed. Run the regression test suite provided with the source code. This will extend the build time.

This flag should normally be disabled, because it is mainly useful for the maintainers, testers and developers.
