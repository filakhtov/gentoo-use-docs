# dev-python/markupsafe

### debug
Append the `-UNDEBUG` option to the `CXXFLAGS` environment variable for the duration of the build (`-DNDEBUG` if the flag is disabled). Enable additional assertions in the C code that will fail and terminate the program if the condition is violated. This is useful for development and debugging purposes.

This flag should normally be disabled.

### test
Run the test suite provided with the source code using the Pytest framework to check for regressions. This will extend a build time.

This flag should normally be disabled as tests are oriented towards the developers, testers and maintainers.
