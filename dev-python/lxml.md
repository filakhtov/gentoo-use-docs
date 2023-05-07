# dev-python/lxml

### debug
Add the `-UNDEBUG` option to the `CPPFLAGS` environment variable for the duration of the build. Build the package with debugging symbols and some additional debugging routines enabled.

This flag should normally be disabled.

### doc
Run the `make html` command to generate API documentation using Sphinx, build additional documentation using the Docutil, and install all the build docs into the `/usr/share/doc/lxml-<VERSION>/` directory.

This flag can be safely disabled.

### examples
Install code examples from the `samples` source tree subdirectory into the `/usr/share/doc/lxml-<VERSION>/examples/` directory.

It is safe to disable the flag.

### test
Execute the `test.py` script to run a test suite provided with a source code after a build is complete and check for regressions. Additional dependencies required to run tests will be installed. This will extend build time.

This flag should normally be disabled as it is only useful for the maintainers, developers and testers.

### threads
The flag is actually never used and should be disabled.
