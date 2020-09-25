# dev-python/pyopenssl

### doc
Use the Python Sphinx documentation generation tool to produce an HTML API documentation and install it into the `/usr/share/doc/pyopenssl-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Execute the `pytest` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the maintainers, developers and testers.
