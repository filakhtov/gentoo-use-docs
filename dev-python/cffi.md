# dev-python/cffi

### doc
Use the Python Sphinx documentation generation tool to produce an HTML API documentation and install it into the `/usr/share/doc/cffi-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Execute the `pytest` tool after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
