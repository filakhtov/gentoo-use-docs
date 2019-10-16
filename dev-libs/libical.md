# dev-libs/libical

### berkdb
Pass the `-DCMAKE_DISABLE_FIND_PACKAGE_BDB=OFF` (`ON` if the flag is disabled) to the cmake build command. Use the `libdb` library to provide an ability to store entries in the Berkeley DB format. This feature is not suitable for production usage, because, according to maintainers, the code path it is enabling has not been fully tested and might contain various bugs.

This flag should normally be disabled.

### doc
Pass the `-DICAL_BUILD_DOCS=ON` option to the CMake build command. Use the Doxygen tool to generate an API documentation and install it together with reference manual.

This flag can be safely disabled.

### examples
Install additional example files into the `/usr/share/doc/libical-<VERSION>/examples` directory. Examples comprise of C source code that demonstrates how to use library for a number of different use cases.

It is safe to disable the flag.

### introspection
Pass the `-DICAL_GLIB=ON` option to the CMake build command. Generate and install the `ICal-3.0.gir` and `ICalGLib-3.0.gir` GIR metadata files to provide dynamic bindings for the `libical` library to languages other than C using the GObject Introspection infrastructure.

This flag can be safely disabled.

### static-libs
Build and install a statically linked version of the `libical`, `libical_cxx`, `libicalss`, `libicalss_cxx`, `libicalvcal` libraries. When disabled, pass the `-DSHARED_ONLY=ON` option to the cmake command to skip building static libraries.

This flag should only ever be enabled if there is an explicit need for the static libraries.

### test
Prepare an environment for the test tool to find a proper version of the Python interpreter. Execute the `ctest` command after the main build is completed to run the regression test suite provided with the source code.

This flag should normally be disabled, as it is mainly useful for maintainers, testers or developers.

### vala
Only works when the `introspection` flag is enabled. Pass the `-DICAL_GLIB_VAPI=ON` option to the CMake build command together with `-DVALAC=` pointing to the selected version of the `valac` binary and `-DVAPIGEN=` pointing to the chosen version of the `vapigen` binary. Generate and install the `libical-glib.vapi` file that provides Vala bindings for the `libical` library using the GObject Introspection.

It is safe to disable this flag if there is no need to use `libical` with Vala based applications.
