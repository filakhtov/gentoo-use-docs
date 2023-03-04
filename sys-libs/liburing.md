# sys-libs/liburing

### examples
Build and install a bunch of example programs that demonstrate how to use the library, e.g. `io_uring-cp`, `io_uring-close-test`, `poll-bench`, etc. When this flag is disabled patch the `Makefile` to skip building and installing any of these tools.

This flag should normally be disabled.

### static-libs
Build and install a statically linked version of the `liburing` library.

This flag should only be enabled if there is a need for the static library.

### test
Build the test suite provided with the source code and run it after the main build is completed to check for any regressions. This will extend the build time. When this flag is disabled, patch the `Makefile` to skip building and running the tests.

This flag should normally be disabled, because these tests are primarily oriented towards the maintainers, developers and testers.
