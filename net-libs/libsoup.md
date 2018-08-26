# net-libs/libsoup

### debug
Pass the `--enable-debug=yes` option to the configure script. Build and install a `libsoup` library with debugging symbols and include additional debugging GLib code into it.

This flag should only be enabled if there is a need to debug the library itself or any dependent apps.

### gssapi
Pass the `--with-gssapi` option to the configure script. Use the `libkrb5` to provides support for the Kerberos (GSS-API - Generic Security Services API) HTTP Authentication.

This flag should only be enabled if there is a need to use Kerberos HTTP authentication via the library.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate the `Soup-2.4.gir` GIR metadata file to provide dynamic bindings for the `libsoup` library to languages other than C.

It is safe to disable the flag.

### samba
Pass the `--with-ntlm-auth=/usr/bin/ntlm_auth` option to the configure script. Use a Samba's `winbind` daemon helper - the `ntlm_auth` tool to provide support for NTLM (NT LAN Manager) single-sign-on authentication.

This flag should be enabled if there is a need to use apps that utilise the `libsoup` library as a client for the NTLM authentication.

### ssl
Ensure that the `ssl` flag is set on the [net-libs/glib-networking](../net-libs/glib-networking.md) package. Provide support for HTTPS (HTTP over TLS) connections via the `gnutls` library.

This flag should be enabled if there are apps that use the `libsoup` library to connect or serve connections over an HTTPS protocol.

### test
Execute the `make check` command when the main build is completed to run a test suite provided with the source code. This will extend the build time. When disabled, patch the `Makefile.in` and `Makefile.am` files to skip building the test related code.

This flag should normally be disabled as it is primarily used by the Gentoo team, testers or developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Generate `Soup-2.4-custom.vala` Vala language bindings for the `libsoup` library.

It is safe to disable the flag.
