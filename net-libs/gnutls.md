# net-libs/gnutls

### cxx
Pass the `--enable-cxx` option to the configure script. Build and install the `libgnutlsxx` library that provides a C++ interface to the GnuTLS library routines. The interface provides the `gnutls` namespace with a set of classes to handle SSL and TLS encrypted connections.

This flag can be safely disabled.

### dane
Pass the `--enable-libdane` option to the configure script. Use the `libdane` library to provide support for the DANE (DNS-Based Authentication of Named Entities) specification defined in the RFC6698 to support TLSA (Transport Layer Security Authentication) entry verification. Build and install the `libgnutls-dane` library - provides an API for DANE certificate verification and the `gnutls/dane.h` include header.

It is safe to disable the flag.

### doc
Generate and install additional documentation in the HTML format into the `/usr/share/doc/gnutls-<VERSION>` directory. Use the `GTK-Doc` to extract a public API documentation for the `libgnutls` library out of comments in a C source code and generate Docbook XML documents and then transform them into an HTML format and install into the system.

This flag can be safely disabled.

### examples
Install a C source code providing examples of how to use the GnuTLS library into the `/usr/share/doc/gnutls-<VERSION>/exmaples` directory. Examples include how to handle return codes of GnuTLS functions, various TLS client implementations, private key and certificate request generation, etc.

It is safe to disable the flag.

### guile
Pass the `--enable-guile` option to the configure script. Build and install the `guile-gnutls-v-2` library - Guile bindings for the GnuTLS library.

This flag should only be enabled if there is a need to run Guile scripts that require the GnuTLS library.

### idn
Pass the `--with-idn` options to the configure script. Use the `libidn2` library to provide support for IDN (Internationalized Domain Names) as described in the IDNA2008 protocol. Allow to properly handle PKIX (X.509) certificates and verification with internationalized domain names.

This flag should only be enabled if there is a need to deal with the IDN.

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to provide an ability to translate programs messages and library strings into various languages based on system locale settings.

This flag should only be enabled if there is a need to use a non-English language.

### openssl
Pass the `--enable-openssl-compatibility` option to the configure script. Build and install the `gnutls-openssl` library - a compatibility layer with the OpenSSL library. This compatibility layer is not complete and it is not intended to completely re-implement the OpenSSL API with GnuTLS. It only provides limited source-level compatibility.

It is safe to disable this flag unless there is a need to use OpenSSL compatiblity layer.

### pkcs11
Pass the `--with-p11-kit` option to the configure script. Use the `p11-kit` library to allow all GnuTLS applications to transparently access smart cards and tokens using the PKCS#11 (Public-Key Cryptography Standard #11) in a thread safe way.

This flag should only be enabled if there is a need to access smart cards or tokens via the GnuTLS library.

### seccomp
This flag only makes sense if the `test` flag is enabled. Pass the `--enable-seccomp-tests` option to the configure script. Build tests that use seccomp sandbox to check if the GnuTLS library can operate under such environment. See `test` flag for details on test execution.

This flag should normally be disabled as these tests are mainly useful for the developers and testers.

### sslv2
Pass the `--enable-ssl2-support` option to the configure script. Enable compatibility layer to provide support for the SSLv2 protocol client "hello messages". It does not provide support for the actual SSLv2 encryption protocol and only allows client and server to negotiate a safe protocol to be used for subsequent communication.

This flag should normally be disabled, unless there is a need to deal with clients emitting SSLv2 Hello messages.

### sslv3
Pass the `--enable-ssl3-support` option to the configure script. Enable support for the SSLv3 encryption protocol.

This flag should be disabled, because SSLv3 is no longer secure due to POODLE attack.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked versions of the GnuTLS libraries, e.g. `libgnutls`, `libgnutlsxx`, etc.

This flag should only be enabled if there is a need for the static libraries.

### test
Pass the `--enable-tests` option to the configure script. Execute the `make check` command after the main build is completed. Build and run a test suite provided with the source code. This will extend a build time. See also the `seccomp`, `test-full` and `valgrind` flags for additional test options.

This flag should normally be disabled as these tests are primarily used by the Gentoo team, developers or testers.

### test-full
This flag only works together with the `test` flag. Pass the `--enable-full-test-suite` option to the configure script. Build and run an extended test suite that tests almost all features provided by the GnuTLS library.

As with the `test` flag, this one should normally be disabled.

### tls-heartbeat
Pass the `--enable-heartbeat-support` to the configure script. Provide support for the HeartBeat - a TLS extension that allows to ping and receive confirmation from the peer described in RFC6520 to allowing the usage of keep-alive functionality without performing a renegotiation.

This flag can be safely disabled.

### tools
Pass the `--enable-tools` option to the configure script. Install various tools:

- if the `dane` flag is enabled, build and install the `danetool` binary - a tool to generate and check DNS resource records for the DANE protocol.
- when the `p11-kit` flag is enabled, build and install the `p11tool` - a program that allows operations on PKCS#11 smart cards and security modules.
- `gnutls-serv` - a simple server program that listens to incoming TLS connections.
- `gnutls-cli-debug` - a TLS debug client. It sets up multiple TLS connections to a server and queries its capabilities.
- `srptool` - a simple program that emulates the programs in the Stanford SRP (Secure Remote Password) libraries using GnuTLS.
- `psktool` - a program  that generates random keys for use with TLS-PSK.
- `gnutls-cli` - a simple client program to set up a TLS connection to some other computer.
- `ocsptool` - a program that can parse and print information about OCSP requests/responses, generate requests and verify responses.
- `certtool` - a tool to generate X.509 certificates, certificate requests, and private keys.

### valgrind
This flag is only working together with the `test` flag. Pass the `--enable-valgrind-tests` option to the configure script. Build and execute additional tests that are using the Valgrind tool to test GnuTLS for memory errors.

As with the `test` flag, this one should normally be disabled.
