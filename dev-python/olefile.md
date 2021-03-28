# dev-python/olefile

### doc
Execute the `make html` command from the `doc` subdirectory of the source tree. Build additional documentation in the HTML format and install it into the `/usr/share/doc/olefile-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Use Python's built-in `unittest` module to run the test suite provided with the source code and check for any regressions after the main build is completed. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, testers and maintainers.
