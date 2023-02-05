# app-crypt/rhash

### debug
Pass the the `--enable-debug` option to the configure script. Build and install binaries and libraries with debugging symbols.

This flag should normally be disabled as it is only useful e.g. for debugging purposes.

### nls
Pass the `--enable-gettext` option to the configure script. Pass the `compile-gmo` option to the `make` command when building the library and `install-gmo` when installing it. Provide an ability to translate programs messages into different languages using Gettext library and install translation files.

It is safe to disable this flag unless there is a need for non-English languages.

### ssl
Pass the `--enable-openssl` option to the configure script. Provide a runtime `--openssl` option to allow replacing hashing algorithms by ones provided by an OpenSSL library. Dynamically load a `libcrypto` library if one is available.

This flag can be safely disabled.

### static-libs
Pass the `--enable-lib-static` option to the configure script. Build and install a statically linked version of the `librhash` library.

It is recommended to disable this flag, unless there is an explicit need for the static library.
