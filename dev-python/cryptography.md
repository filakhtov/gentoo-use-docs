# dev-python/cryptography

### libressl
Normally, this package uses the `OpenSSL` library as an underlying backend for cryptographic operations. Enabling this flag would allow to use the `LibreSSL` library instead.

This flag should only be toggled system-wide, because both libraries can't be installed on the same system.

### test
Execute the `pytest` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the maintainers, developers and testers.
