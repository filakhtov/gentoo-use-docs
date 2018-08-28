# sys-libs/ldb

### ldap
Does nothing when enabled as a LDAP support is enabled by default. When disabled, pass a `--disable-ldap` option to a WAF configure script. Enable support for a remote LDAP (Lightweight Directory Access Protocol) backend.

This flag should be enabled if there is a need to connect to a remote LDAP server for storing and retrieving data.

### python
Set-up proper Python environment for a WAF configure script. When disabled, pass a `--disable-python` option to the WAF configure script. Build and install an `ldb` Python module that provides bindings for the `libldb` library.

This flag should be enabled if there is a need to access LDB resources in Python scripts.

### doc
Use a Doxygen tool to generate an API documentation and install it into the `/usr/share/doc/ldb-<VERSION>/html` directory. Additionally, install man pages with an API description.

It is safe to disable the flag.
