# dev-lang/python-exec

### native-symlinks
Install a generic version symlinks (i.e. `python` and `python3`) pointing to the approprriate Python interpreter version, `python3.X`. With this flag disabled only `python3.X` executables will be installed and any scripts that point to `python` or `python3` won't work.

It is recommended to enable this flag.

### test
Execute the `pytest` tool after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
