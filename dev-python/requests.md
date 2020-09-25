# dev-python/requests

### socks5
Pull in the [dev-python/PySocks](../dev-python/PySocks.md) package as a dependency to enable support for SOCKS5-proxied connections.

It is safe to disable this flag.

### ssl
Pull in the [dev-python/cryptography](../dev-python/cryptography.md) package as a dependency to enable support for HTTPS (Hypertext Transfer Protocol Secure) connections, including browser-style SSL certificate verification.

This flag should normally be enabled.

### test
Execute the `pytest` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the maintainers, developers and testers.
