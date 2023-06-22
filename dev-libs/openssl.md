# openssl

### asm
Passes the `enable-asm` argument to the `Configure` script. This uses an assembly code instead of a C code to accelerate encryption and decryption of the most important ciphers. Enabling this optimization has a huge performance impact.

It is recommended to enable this flag.

### fips
Pass the `enable-fips` argument to the `Configure` script. Build and install OpenSSL FIPS modules, which provides a specific subset of OpenSSL that has gone through FIPS (Federal Information Processing Standard Publication) 140-2 validation. Execute the `make install_fips` to install the FIPS module into the system after the main build is completed.

This flag should only be enabled if there is a need to achieve FIPS-compliance, because any change in FIPS needs to be revalidated, meaning bugs and vulnerabilities take longer to fix compared to the standard OpenSSL builds.

### klts
Pass the `enable-ktls` argument to the `Configure` script. Enable support for kTLS (Kernel Transport Layer Security), allowing to offload cryptographic operations to the supported Kernels to significantly improve performance by eliminating the need to copy data from the kernel space, encrypt or decrypt in user space and copy it back for transport.

It is recommended to enable this flag on supported systems.

### rfc3779
This flag passes the `enable-rfc3779` argument to the `Configure` script. It enables support for RFC-3779 (aka X.509 Extensions for IP Addresses and AS Identifiers).

This flag is safe to disable unless it is required to use an IP address as a subject name for X.509 certificates.

### sctp
Passes the `enable-sctp` argument to the `Configure` script. The flag enables support for TLS encrypted connections over the SCTP (Stream Control Transmission Protocol).

It is recommended to keep this flag disabled, unless TLS encrypted SCTP connections are required.

### static-libs
Static libraries (`*.a` files) are built by default but are removed by an ebuild before installation. Enabling the flag will preserve these libraries and install them into the target system.

This flag should be disabled unless there is a specific need for static libraries, e.g. for development purposes.

### test
Build the test suite provided with the source code and executes the `make test` command after the main build is completed to run it and check for any regressions. This will extend the build time. When this flag is disabled, pass the `no-tests` option to the `Configure` script to avoid building the test suite.

The flag should be disabled. It is mainly useful for Gentoo developers and testers.

### tls-compression
Passes the `enable-zlib` argument to the `Configure` script. Enables support for a clear-text compression and decompression before the encryption and after the decryption using zlib library. Compression is enabled by default when this flag is enabled.

It is safe to disable the flag unless there is a need to establish encrypted connections with a compression support.

### vanilla
Enabling this flag will ensure that no Gentoo-specific patches are applied to the source code before compilation.

It is not recommended to enable the flag as it might result in a broken build or misbehaving binaries and libraries.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### weak-ssl-ciphers
Pass the `enable-weak-ssl-ciphers` option to the `Configure` script. By default modern OpenSSL library is built without any "EXPORT" or "LOW" strength ciphers, as they are considered insecure. When this flag is enabled, support for these ciphers will be built into the resulting library.

It is recommended to disable this flag, unless there is an explicit need to use these insecure ciphers.
