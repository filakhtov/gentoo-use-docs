# www-client/lynx

### bzip2
Pass the `--with-bzlib` option to the configure script. Use the `libbz2` library to support a BZip2 compressed content, aka `Content-Encoding: bzip2` (and `x-bzip2`) header.

This flag should be enabled if there is a need to fetch BZip2 compressed content.

### cjk
Pass the `--enable-cjk` option to the configure script. Enable support for the raw CJK (Chinese, Japanese, Korean) mode that assumes that 8-bit characters are appropriate for the display character set and no reverse translation is necessary.

This flag should be enabled if there is a need to deal with Asian pages or websites.

### gnutls
Only works if the `ssl` flag is enabled. Pass the `--with-gnutls` (instead of the `--with-ssl`) option to the configure script. Use the GnuTLS library (in place of OpenSSL) to enable an experimental support for HTTPS (Hyper Text Transfer Protocol Secure) connections.

This flag should normally be disabled, because GnuTLS support is in an experimental state.

### idn
Pass the `--enable-idna` option to the configure script. Use the `libidn` library to provide support for the IDN (internationalized domain name) to allow using native character sets for domain names.

This flag should be enabled if there is a need to access IDN names.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable support for the IPv6 protocol to provide an ability to access IPv6-enabled websites.

This flag should be enabled if there is a need to access IPv6-enabled websites.

### libressl
This flag allows to use the LibreSSL library over the OpenSSL one to provide HTTPS connections support.

This flag should be toggled systemwide, because only one of these libraries can be installed at the same time.

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to provide an ability to translate programs messages into different languages based on the system locale settings.

This flag should be disabled, unless there is a need to use Lynx in a non-English language.

### ssl
Pass the `--with-ssl` option to the configure script. Use the OpenSSL library to provide support for HTTPS (Hyper Text Transfer Protocol Secure) connections.

This flag should normally be enabled, otherwise no HTTPS connections will be possible.

### unicode
Pass the `--with-screen=ncursesw` option (instead of `ncurses`) to the configure script. Use the "wide" version of the ncurses library to support multibyte character encodings. Modify the `lynx.cfg` configuration file to set default character set to UTF-8.

This flag should be normally enabled as the Unicode is mainstream nowadays.
