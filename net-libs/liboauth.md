# net-libs/liboauth

### bindist
Make sure that the NSS library is used for cryptography instead of OpenSSL to avoid licensing issues with binary distributions of the compiled packages.

This flag should be enabled if there is a need to redistribute the library in the binary form.

### curl
Pass the `--enable-libcurl` option to the configure script. Link against the `libcurl` library and use it to perform all HTTP(S) communications. Requires the [net-misc/curl](../net-misc/curl.md) to have the `ssl` flag disabled or otherwise cryptographic backend must match, i.e. if the `nss` flag is enabled then NSS, otherwise the OpenSSL. When this flag is disabled, the library will shell out to the `curl` command-line util instead of using the `libcurl` library directly.

It is recommended to enable this flag, unless there is a need to use incompatible cryptographic backend.

### doc
Use the Doxygen tool to generate additional documentation in the HTML format and install it into the `/usr/share/doc/liboauth-<VERSION>/html` directory. Documentation is primarily oriented towards developers who want to use this library.

It is safe to disable the flag.

### nss
Pass the `--enable-nss` option to the configure script. Use the `libnss` library to perform hashing, singing and generating nonce. When disabled, the OpenSSL library will be used instead.

This flag can be safely disabled, however it must be enabled if there is a need to redistribute the binary package.
