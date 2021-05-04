# net-misc/socat

### bindist
This flag ensures that combination of other flags aren't preventing resulting binary package from being redistributed, because the OpenSSL and Readline libraries have conflicting licenses.

This flag should be enabled if there is a need to redistribute the binary package.

### ipv6
Pass the `--enable-ip6` option to the configure script. Enable support for the IPv6 protocol and provide an ability to use relevant address types: `tcp6`, `udp6`, `tcp6-connect`, `tcp6-listen`, `udp6-datagram` and others.

This flag should be enabled if there is a need to establish connections over an IPv6-enabled network.

### readline
Pass the `--enable-readline` option to the configure script. Use the `libreadline` library to provide an ability to track command history, improve command editing, and allow to search and recall previously entered commands. Enable support for the `READLINE` address type to enable aforementioned features.

It is safe to disable the flag if there is no need for improved interactive editing experience.

### ssl
Pass the `--enable-openssl` option to the configure script. Provide an ability to encrypt connection between two hosts using the OpenSSL library. Enable support for the `openssl` and `openssl-listen` address types to establish encrypted connections.

This flag should be enabled if there is a need for an SSL encrypted transport.

### tcpd
Pass the `--enable-libwrap` option to the configure script. Use the `libwrap` library to enable support for TCP wrappers and provide an ability to allow or deny specific TCP connections with ACL file entries.

This flag should normally be disabled as Linux firewall (almost always) is a better alternative.
