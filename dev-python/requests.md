# dev-python/requests

### socks5
Pull in the [dev-python/PySocks](../dev-python/PySocks.md) package as a dependency to enable support for SOCKS5-proxied connections.

It is safe to disable this flag.

### test
Execute the `pytest` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the maintainers, developers and testers.

### test-rust
Only makes sense if the `test` flag is enabled. Pull in the [dev-python/trustme](../dev-python/trustme.md) package as a dependency to provide fake CA (Certificate Authority) and TLS certificates (Transport Layer Security) that will be used to run tests that are dealing with encrypted connections, otherwise they will be skipped.

It safe to disable this flag.
