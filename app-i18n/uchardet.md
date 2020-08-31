# app-i18n/uchardet

### static-libs
Pass the `-DBUILD_STATIC=true` option to the cmake command. Build and install a statically linked version of the `libuchardet` library.

This flag should be disabled, unless there is an explicit need for the static library.

### test
Compile and run the test suite provided with the source code after the main build is completed to check for any regressions. When this flag is disabled, modify the `CMakeLists.txt` file and comment out the `test` directory to prevent tests from being built and executed.

This flag should normally be disabled, as they are primarily useful for maintainers, testers and developers.
