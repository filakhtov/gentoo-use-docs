# dev-cpp/glibmm

### debug
Pass the `-Ddebug-refcounting=true` option to the meson build script script. Define additional macro to enable debugging reference counting and produce additional messages at runtime when adding and removing object references.

This flag should only be enabled for debugging purposes.

### doc
Pass the `-Dbuild-documentation=true` option to the meson build script. Generate documentation in the HTML format using the Doxygen tool, including an API documentation, description of the modules, namespaces, classes and their inheritance diagrams, etc, and install it into the `/usr/share/doc/glibmm-<VERSION>` directory and install example C++ source code into the `examples` subdirectory that shows how to use the glibmm library for variety of different use cases.

It is safe to disable the flag.

### test
Execute the `meson test` command to build the test suite provided with the source code and execute it after the main build is completed to check for any regressions.

This flag should normally be disabled as it is intended for testers, developers and maintainers.
