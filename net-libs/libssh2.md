# net-libs/libssh2

### gcrypt
This flag conflicts with and takes precedence over the `libressl` and `mbedtls` flags. When enabled, pass the `-DCRYPTO_BACKEND=Libgcrypt` option to the CMake build command. Use the gcrypt library (instead of the OpenSSL) to perform cryptographic operations.

This flag can be safely disabled, unless there is a specific need to use the gcrypt library as a crypto backend.

### libressl
This flag conflicts with the `libressl` and `mbedtls` flags and will be ignored if one of them is enabled. When the flag is enabled, pass the `-DCRYPTO_BACKEND=OpenSSL` (which is default) option to the CMake build command. This flag allows to use the LibreSSL library (instead of the OpenSSL) to perform cryptographic operations.

This flag should normally be disabled and must only be enabled system-wide, because OpenSSL and LibreSSL libraries can't be simultaneosly installed onto the same system.

### mbedtls
This flag conflicts with the `libressl` and `mbedtls` flags. It takes precedence over the `libressl` flag, but has lower priority than the `gcrypt` flag. If enabled, pass the `-DCRYPTO_BACKEND=mbedTLS` option to the CMake build command. Use the mbedTLS library (instead of the default OpenSSL) to perform cryptographic operations.

It is recommended to disable this flag, unless there is an explicit need to configure the libssh2 library to use the mbedTLS backend.

### zlib
Pass the `-DENABLE_ZLIB_COMPRESSION=yes` (`no` when the flag is disabled) option to the CMake build command. Use the `libz` library to perform payload compression, instead of using internal minimalist (no compression) implementation.

This flag can be safely disabled, however no proper compression will be performed in this case.
