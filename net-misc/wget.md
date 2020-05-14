# net-misc/wget

### cookie_check
Pass the `--with-libpsl` option to the configure script. This provides an ability to check for valid cookie domains using a public suffix list.

It is safe to disable this flag, however it can provide some security benefits if `wget` to be used with cookies.

### debug
Passes the `--enable-debug` option to the configure script. The resulting `wget` binary will have a support for the `--debug` runtime option that is producing a lot of debugging information as requests are executed.

This flag is safe to disable.

### gnutls
This flag only has an effect if an `ssl` flag is enabled too. Passes the `--with-ssl=gnutls` option to the configure script. This will use the GnuTLS library for handling HTTPS connections instead of the OpenSSL one.

It is safe to disable this flag.

### idn
The flag passes the `--with-idn` and the `--enable-iri` options to the configure script. Enables support for the IRI (Internationalized Resource Identifier, RFC 3987) protocol.

This flag can safely be disabled if there is no need to deal with internationalized domain names (ones that have non-English characters in them).

### ipv6
Passes the `--enable-ipv6` option to the configure script. This enables the IPv6 protocol support.

The flag can safely be disabled unless the target system has to participate in the IPv6-enabled network.

### libressl
This flag replaces an SSL backend for handling HTTPS connections with the LibreSSL library instead of the OpenSSL one. Only has an effect if an `ssl` flag is enabled too.

The flag should only be enabled systemwide, because the OpenSSL and the LibreSSL libraries can't be installed at the same time.

### metalink
Pass the `--with-metalink` option to the configure script. Enable support for downloading files using the metalink extensible metadata file format, that provides a list of resources for a file (URLs for all the mirrors and P2P resources) along with checksums and other metadata.

It is safe to disable this flag, because metalink is not widely adopted.

### nls
The flag will pass the `--enable-nls` option to the configure script. This is used to provide the translation and the localization for variety of languages.

This flag is safe to disable unless there is a need to use wget in non-English language.

### ntlm
Passes the `--enable-ntlm` option to the configure script. Enables the NTLM (NT LAN Manager) authorization support for the HTTP protocol.

It is recommended to disable this flag unless NTLM authorization support is required.

### pcre
Normally `wget` supports POSIX Regular Expressions for the `--accept-regex` and the `--reject-regex` options that are used to filter files during recursive retrieval. Enabling this flag passes the `--enable-pcre` option to the configure script thus providing support for the `--regex-type` and PCRE regular expressions for the aforementioned options.

It is safe to disable this flag, unless PCRE support for the `--accept-regex` and the `--reject-regex` is desired.

### ssl
Passes the `--enable-digest`, the `--enable-opie` and the `--with-ssl=openssl` flags to the configure script. Enables the HTTPS protocol support, an HTTP digest authorization, and an opie or an s/key FTP login. The OpenSSL library is used as a default SSL backend.

It is recommended to keep this flag enabled, otherwise an HTTPS support will not be available.

### static
Enabling this flag will will produce the static `wget` binary and requires all dependency libraries to be statically linked in order to be able to do so.

The flag should normally be disabled, unless there is a specific use case that require the statically linked `wget` binary.

### test
This flag instructs portage to execute a test suite provided with the source code after the build is finished. A number of additional dependencies is required in order to run these tests. The build time will also be increased.

This flag should be disabled and is only useful for the Gentoo team, developers and testers.

### uuid
The flag passes the `--with-libuuid` option to the configure script. This will use the `libuuid` to generate UUIDs required for `WARC-Record-Id` header when saving a request and a response data in the WARC (Web ARChive) file format. Disabling this flag will use a fallback mechanim to generate UUID formatted strings based on random numbers.

Disabling this flag is safe, but is not recommended if there is a need to save data in WARC format.

### zlib
Passes the `--with-zlib` option to the configure script. Enables support for compressing resulting WARC archives. With this flag a compression is enabled by default and the `--no-warc-compression` runtime option will be provided to disable it.

It is safe to turn off this flag.
