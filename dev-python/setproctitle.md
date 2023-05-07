# dev-python/setproctitle

### debug
Add the `-UNDEBUG` option to the `CPPFLAGS` environment variable for the duration of the build. Build the package with debugging symbols and some additional debugging routines enabled.

This flag should normally be disabled.

### test
Execute the `pytest` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled as it is primarily used by the maintainers, testers or developers.
