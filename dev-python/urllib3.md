# dev-python/urllib3

### brotli
Pull in the [dev-python/brotlipy](../dev-python/brotlipy.md) package as a dependency to enable support for the Brotli compression algorithm, that is created by Google with better compression than gzip and deflate and a comparable speed.

This flag can be safely disabled.

### doc
Use the Python Sphinx documentation generation tool to produce an HTML API documentation and install it into the `/usr/share/doc/urllib3-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Execute the `pytest` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the maintainers, developers and testers.
