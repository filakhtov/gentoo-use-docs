# openssl

### asm
Passes the `enable-asm` argument to the `Configure` script. This uses an assembly code instead of a C code to accelerate encryption and decryption of the most important ciphers. Enabling this optimization has a huge performance impact.

It is recommended to enable this flag.

### bindist
There are licensing restrictions on binary distribution of the OpenSSL library compiled with ECC (Elliptic Curve Cryptography), such as SM2 (defined by the Chinese national standard GM/T 0003-2012). The flag is passing the `no-ec2m` and `no-sm2` arguments to the `Configure` script and this disables patented algorithms allowing the resulting binary package to be distributed. When disabled, passes the `enable-ec2m` and `enable-sm2` argument instead.

This flag should normally be disabled as the ECC brings a lot of benefits. It should, however, be disabled if it is necessary to distribute compiled binaries.

### gmp
The flag passes the `enable-gmp` and the `-lgmp` arguments to the `Configure` script. This will replace OpenSSL built-in RSA private key operations with GMP library routines.

In a past the GMP library used to provide performance benefits over an OpenSSL implementation. It is no longer true nowadays at least on x86 platform. This flag is not recommended any longer.

### kerberos
Passes the `enable-krb5` and the `--with-krb5-flavor=<backend>` arguments to the Configure script. The `<backend>` value can be either `MIT` if the [app-crypt/mit-krb5](../app-crypt/mit-krb5.md) package is installed or `Heimdal` otherwise. The flag enables Kerberos ciphersuite support in OpenSSL.

This flag provides OpenSSL routines for Kerberos an authentication and encryption support. It is safe to disable the flag unless Kerberos support is required.

### rfc3779
This flag passes the `enable-rfc3779` argument to the `Configure` script. It enables support for RFC-3779 (aka X.509 Extensions for IP Addresses and AS Identifiers).

This flag is safe to disable unless it is required to use an IP address as a subject name for X.509 certificates.

### sctp
Passes the `enable-sctp` argument to the `Configure` script. The flag enables support for TLS encrypted connections over the SCTP (Stream Control Transmission Protocol).

It is recommended to keep this flag disabled, unless TLS encrypted SCTP connections are required.

### sslv3
This flag is passing the `enabled-ssl3` and `enable-ssl3-method` arguments to the `Configure` script. It enables an SSLv3 (Secure Socket Layer version 3) cryptographic protocol support.

It is strongly recommended to disable the flag, because an SSLv3 is vulnerable, insecure and should not be used nowadays.

It should only be enabled if there is an absolute need for SSLv3 support and all applications except affected ones should have it disabled via configuration.

### static-libs
Static libraries (`*.a` files) are built by default but are removed by an ebuild before installation. Enabling the flag will preserve these libraries and install them into the target system.

This flag should be disabled unless there is a specific need for static libraries, e.g. for development purposes.

### test
Executes `make -j1 test` after the build is finished. This will run a test suite provided with OpenSSL sources. Enabling this flag will increase a build time.

The flag should be disabled. It is mainly useful for Gentoo developers and testers.

### tls-heartbeat
This flag passes the `enable-heartbeats` argument to the `Configure` script. Enables the TLS Heartbeat protocol support as described in the RFC6520 to keep an encrypted connection alive without performing a renegotiation.

The flag can be safely disabled. It might be necessary to enable it under certain network setups, e.g. where a firewall eagerly closes inactive connections.

### vanilla
Enabling this flag will ensure that no Gentoo-specific patches are applied to the source code before compilation.

It is not recommended to enable the flag as it might result in a broken build or misbehaving binaries and libraries.

### zlib
Passes the `enable-zlib` argument to the `Configure` script. Enables support for a clear-text compression and decompression before the encryption and after the decryption using zlib library. Compression is enabled by default when this flag is enabled.

It is safe to disable the flag unless there is a need to establish encrypted connections with a compression support.
