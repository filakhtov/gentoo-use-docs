# dev-libs/msgpack

### doc
Run the `make doxygen` command to generate API documentation from the source code and annotations using the Doxygen tool. This will generate the documentation in the HTML format and install it on your system.

### examples
Install additional example source code that demonstrates how to use the library.

This flag should normally be disabled, because these examples are intended for the developers and not the end users.

### test
Pass the `-DMSGPACK_BUILD_TESTS=true` option to the cmake command to build a test suite provided with the source code. Run the `make test` command after the main build is completed to run the tests and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
