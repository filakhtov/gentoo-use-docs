# net-misc/curl

### adns
Pass the `--enable-ares` option to the configure script. Use a `c-ares` library for asynchronous DNS requests. Note, that a `c-ares` tends to fail in unstable network configurations and sometimes under high load.

This flag can be safely disabled.

### alt-svc
Pass the `--enable-alt-svc` option to the configure script. Enable support for HTTP Alternative Services (aka `Alt-Svc` header) which was added to cURL as a prerequisite for the HTTP/3 protocol support.

This flag should normally be disabled.

### brotli
Pass the `--with-brotli` option to the configure script. Enable support for a `brotli` compression algorithm introduced by Google (provides 14% to 21% better compression than `gzip`) that recently becoming popular.

It is safe to disable this flag, however it can benefit users who have data constraints.

### http2
Pass the `--with-nghttp2` option to the configure script. Modify a pkg-config `libcurl.pc` file to remove `-lnghttp2` option from a `Libs.private` keyword and append a `libnghttp2` value to a `Requires.private` keyword. Provides support for an HTTP/2 protocol using a `nghttp2` library.

This flag should be enabled if there is a need to support HTTP/2 protocol via a `curl` command line tool or a `libcurl` library. It is safe to disable otherwise.

### idn
Pass the `--with-libidn2` option to the configure script. Enable support for an IDN (internationalized domain names). Provide an ability to use domain names that contain characters from language-specific scripts or alphabet.

This flag can be safely disabled if there is no need to deal with non-English characters in domain names or if a Punycode is used to access such domains.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable support for an IPv6 protocol.

This flag should be enabled if the target system participates in IPv6 capable networks. It can be safely disabled otherwise.

### kerberos
Pass the `--with-kerberos=/usr` option to the configure script. Provide support for a Kerberos authentication protocol using a GSS-API for an HTTP and to some extent for an FTP protocols.

This flag should only be enabled if there is a need to use Kerberos authentication protocol. It can safely be disable otherwise.

### ldap
Pass the `--enable-ldap` and the `--enable-ldaps` options to the configure script. Provide an ability to query LDAP servers (e.g. Active Directory) via a `ldap://` or a `ldaps://` shemes.

This flag should normally be disabled unless there is a need to access LDAP servers using cURL.

### metalink
Pass the `--with-metalink` option to the configure script. Enable a Metalink support - an extensible metadata format for downloading files that provides file verification, data corruption recovery and alternate download sources.

It is safe to disable this flag unless there is a need to download files using Metalinks via cURL.

### nghttp3
Pass the `--with-nghttp3` and `--with-ngtcp2` options to the configure script. Enable support for the QUIC protocol using the `ngtcp2` library to implement the HTTP/3 protocol on top of it using the `nghttp3` library and enable the `--http3` runtime option to access this feature.

This flag should normally be disabled, because HTTP/3 support is considered experimental at this stage.

### progress-meter
Pass the `--enable-progress-meter` option to the configure script. Enable progress meter that shows how transfer (either upload or download) is progressing, including the current transfer speed, elapsed time and estimated time to completion.

It is safe to disable the flag if there is no need to monitor transfer progress with cURL.

### quiche
Pass the `--with-quiche` option to the configure script. Use the `quiche` library to enable support for the HTTP/3 protocol on top of the QUIC protocol and enable the `--http3` runtime option to access this feature.

This flag should normally be disabled, because HTTP/3 support is considered experimental at this stage.

### rtmp
Pass the `--with-librtmp` option to the configure script. Provide support for an RTMP protocol using an `rtmp://` scheme and allow to download stream media.

This flag can be safely disabled as it is only necessary for downloading stream video/audio using RTMP protocol.

### samba
Pass the `--enable-smb` option to the configure script. Enable support for an SMB protocol. Provide an `smb://` scheme support to download files from Windows shares or Samba servers.

It is safe to disable this flag as it is only necessary when using cURL for downloading files from SMB protocol.

### ssh
Pass the `--with-libssh2` option to the configure script. Provide support for SCP and SFTP protocols using a `libssh2` library. Enable an `scp://` and an `sftp://` shemes to download files from an SSH server.

This flag should normally be disabled unless there is a need to use a curl command line tool or a library to download files from SSH servers.

### ssl
This flag does nothing on its own. It enforces one of the ssl backends to be enabled via `CURL_SSL` use flags.

It is recommended to enable this flag as it provides vital functionality, e.g. HTTPS protocol support.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libcurl` library.

This flag should normally be disabled unless there is an explicit need for static library, e.g. for development purposes.

### test
Execute a test suite provided with a source code by running `make check` command after build is complete. This will extend a build time.

It is recommended to keep this flag disabled as it is only required by the Gentoo team, developers and testers.

### threads
Pass the `--enable-threaded-resolver` and the `--enable-pthreads` options to the configure script. Enable cURL's builtin threaded DNS resolver (built on top of POSIX threads or Windows threads). Switch to non-blocking name resolution and prevent timeouts during resolution.

This flag can be safely disabled, however it is enabled by default by upstream nowadays and can help avoid timeouts with a slow DNS.
