# dev-libs/icu

### debug
Pass the `--enable-debug` option to the configure script. Append the `-g` flag to the `CFLAGS` and `CXXFLAGS` variables to produce libraries with debugging symbols. Include additional debugging code to disable compiler warnings, enable runtime assertions, prevent some compiler optimizations, etc.

This flag should only ever be enabled for debugging purposes.

### doc
Use the Doxygen tool to generate library API documentation in the HTML format and install it into the `/usr/share/doc/icu-<VERSION>/html` directory. Documentation provides Class Hierarchy, Alphabetical List and Compound List for C++ classes and Module List and File Members for C.

It is safe to disable the flag.

### examples
Pass the `--enable-samples` option to the configure script. Install additional sample code that demonstrates how to use the `libicu` library for different use cases, including calendar handling, Unicode case conversion, character set detection, usage of the number and message formats, regular expressions, etc.

This flag can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libicudata`, `libicui18n`, `libicuio`, `libicutest`, `libicutu` and the `libicuuc` libraries.

This flag should only be enabled if there is an explicit need for the static libraries.
