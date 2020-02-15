# sys-libs/ldb

### doc
Use a Doxygen tool to generate an API documentation and install it into the `/usr/share/doc/ldb-<VERSION>/html` directory. Additionally, install man pages with an API description.

It is safe to disable the flag.

### ldap
Does nothing when enabled as a LDAP support is enabled by default. Enable support for a remote LDAP (Lightweight Directory Access Protocol) backend. When disabled, pass a `--disable-ldap` option to a WAF configure script.

This flag should be enabled if there is a need to connect to a remote LDAP server for storing and retrieving data.

### lmdb
Enable the new LMDB backend which, unlike TDB, can handle databases larger than 4Gb and provides other useful improvements. When disabled, pass a `--without-ldb-lmdb` option to a WAF configure script.

It is recommended to disable the flag, because LMDB backend is currently experimental and not ready for production use.

### python
Set-up proper Python environment for a WAF configure script. Build and install an `ldb` Python module that provides bindings for the `libldb` library. If the flag is disabled, pass a `--disable-python` option to the WAF configure script.

This flag should be enabled if there is a need to access LDB resources in Python scripts.

### test
Execut the `waf test` command when the main build is completed to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag can be safely disabled, because it is primarily useful for developers, maintainers and testers.
