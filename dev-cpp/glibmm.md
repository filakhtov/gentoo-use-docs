# dev-cpp/glibmm

### debug
Pass the `--enable-debug-refcounting` option to the configure script. Define additional macro to enable debugging reference counting and produce additional messages at runtime when adding and removing object references.

This flag should only be enabled for debugging purposes.

### doc
Pass the `--enable-documentation` option to the configure script. Generate documentation in the HTML format using the Doxygen tool, including an API documentation, description of the modules, namespaces, classes and their inheritance diagrams, etc, and install it into the `/usr/share/doc/glibmm-<VERSION>` directory. Also install example C++ source code into the `examples` subdirectory that shows how to use the glibmm library for variety of different use cases.

It is safe to disable the flag.

### test
Execute the `make check` command from the `tests` directory to build various test suites provided with the source code when the main build is completed. Run resulting `test` binaries from every subdirectory to check for regressions and make sure they pass successfully. This will extend a build time. When disabled, patch the `Makefile.am` and `Makefile.in` files to skip building any test files.

This flag should normally be disabled as it is intended for testers, developers and the Gentoo team.
