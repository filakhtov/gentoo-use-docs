# dev-python/cryptography

### idna
Pull in the [dev-python/idna](../dev-python/idna.md) package as a dependency to provide support for the IDNA (Internationalized Domain Names in Applications) protocol, i.e. written using a language-specific script or alphabet, such as Arabic, Chinese, Cyrillic, Devanagari, Hebrew or the Latin alphabet-based characters with diacritics or ligatures, such as French.

This flag can be safely disabled if there is no need to access domain names written in non-Latin alphabet.

### libressl
Normally, this package uses the `OpenSSL` library as an underlying backend for cryptographic operations. Enabling this flag would allow to use the `LibreSSL` library instead.

This flag should only be toggled system-wide, because both libraries can't be installed on the same system.

### test
Execute the `pytest` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the maintainers, developers and testers.
