# app-crypt/rhash

### debug
Append the `-DNDEBUG` option to the `ADDCFLAGS` variable and pass it to the `make` command. Build and install binaries and libraries with debugging symbols.

This flag should normally be disabled as it is only useful e.g. for debugging purposes.

### libressl
This flag only works if an `ssl` flag is enabled. Use LibreSSL library instead of default OpenSSL one.

This flag should be toggled system-wide, as the only one of these libraries can be installed on the same system at a time.

### nls
Append the `-DUSE_GETTEXT` option to the `ADDCFLAGS` variable and pass it to the `make` command. Execute a `make install-gmo` command. Provide an ability to translate programs messages into different languages using Gettext library and install translation files.

It is safe to disable this flag unless there is a need for non-English languages.

### ssl
Append the `-DOPENSSL_RUNTIME` and the `-rdynamic` options to the `ADDCFLAGS` and `-ldl` to the `LDFLAGS` variables and pass them to the `make` command. Provide a runtime `--openssl` option to allow replacing hashing algorithms by ones provided by an OpenSSL library. Dynamically load a `libcrypto` library if one is available.

This flag can be safely disabled.

### static-libs
Execute a `make lib-static` command during a build. Build and install a statically linked `librhash` library.

It is recommended to disable this flag, unless there is an explicit need for the static library.
