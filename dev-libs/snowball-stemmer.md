# dev-libs/snowball-stemmer

### static-libs
Build and install a statically linked version of the `libstemmer` library.

This flag should normally be disabled, unless there is an explicit need for the static library.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the developers, maintainers and testers.
