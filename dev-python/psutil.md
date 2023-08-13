# dev-python/psutil

### debug
Append the `-UNDEBUG` option to the `CXXFLAGS` environment variable for the duration of the build (`-DNDEBUG` if the flag is disabled). Enable additional assertions in the C code that will fail and terminate the program if the condition is violated. This is useful for development and debugging purposes.

This flag should normally be disabled.

### test
Execute the `psutil/tests/runner.py` Python script after the main build is completed from the build directory to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag should normally be disabled, as it is mainly useful for developers, testers or maintainers.
