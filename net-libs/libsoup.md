# net-libs/libsoup

### brotli
Pass the `-Dbrotli=enabled` (`disabled` when the flag is disabled) option to the meson build script. Enable support for Google's Brotli generic-purpose lossless compression algorithm and advertise such support by sending an appropriate `Accept-Encoding` header to the server.

It is safe to disable this flag if Brotli encoding support is not required.

### gssapi
Pass the `-Dgssapi=enabled` (`disabled` if the flag is disabled) option to the meson build script. Use the `libkrb5` to provides support for the Kerberos (GSS-API - Generic Security Services API) HTTP Authentication.

This flag should only be enabled if there is a need to use Kerberos HTTP authentication via the library.

### gtk-doc:2.4
Pass the `-Dgtk_doc=true` (`false` if the flag is disabled) option to the meson build script. Use the Gtk-Doc tool to generate an API reference documentation in the HTML format and install it into the `/usr/share/gtk-doc` directory.

It is safe to disable this flag if there is no need for developer documentation.

### gtk-doc:3.0
Pass the `-Ddocs=enabled` (`disabled` if the flag is disabled) option to the Meson build script. Use the Gtk-Doc tool to generate an API reference documentation in the HTML format and install it into the `/usr/share/gtk-doc` directory.

This flag can be safely disabled.

### introspection
Pass the `-Dintrospection=enabled` (`disabled` when this flag is disabled) option to the meson build script. Generate the `Soup-2.4.gir` GIR metadata file to provide dynamic bindings for the `libsoup` library to languages other than C.

It is safe to disable the flag.

### samba
Pass the `-Dntlm=enabled` (`disabled` if the flag is disabled) option to the meson build script. Use a Samba's `winbind` daemon helper - the `ntlm_auth` tool to provide support for NTLM (NT LAN Manager) single-sign-on authentication.

This flag should be enabled if there is a need to use apps that utilise the `libsoup` library as a client for the NTLM authentication.

### ssl
Ensure that the `ssl` flag is set on the [net-libs/glib-networking](../net-libs/glib-networking.md) package. Provide support for HTTPS (HTTP over TLS) connections via the `gnutls` library.

This flag should be enabled if there are apps that use the `libsoup` library to connect or serve connections over an HTTPS protocol.

### sysprof
Pass the `-Dsysprof=enabled` (`disabled` when this flag is disabled) option to the meson build script. Enable support for sending profiling data to sysprof for all performed network requests.

This flag should only be enabled if there is a need to perform application profiling using sysprof tool.

### test:2.4
Pass the `-Dtests=true` option to the meson build script. Execute the `meson test` command when the main build is completed to run a test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled as it is primarily used by the maintainers, testers or developers.

### test:3.0
Pass the `-Dtests=true` and `-Dpkcs11_tests=enabled` options to the Meson build script. Execute the `meson test` command when the main build is completed to run a test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled as it is primarily used by the maintainers, testers or developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `-Dvapi=enabled` (`disabled` when the flag is disabled) option to the configure script. Generate `Soup-2.4-custom.vala` Vala language bindings for the `libsoup` library.

It is safe to disable the flag.
