# dev-libs/check

### doc
Use the Doxygen tool to generate the library API documentation in the HTML format from the source code annotations and install it into the system.

It is safe to disable this flag.

### subunit
Pass the `-DCHECK_ENABLE_SUBUNIT=ON` option to the CMake build command. Enable support for the subunit test protocol, i.e. producing an output that is compatible with subunit output. This can be useful to combine test results from multiple languages, or to perform programmatic analysis on the results of multiple check test suites or otherwise handle test results in a programmatic manner.

It is safe to disable this flag.

### test
Pass the `-DBUILD_TESTING=ON` option to the CMake build command. Execute the `ctest` command after the main build is completed to run the test suite provided with the source code and check for any regressions.

This flag should normally be disabled as it is primarily useful for developers, maintainers and testers.
