# net-libs/libtirpc

### ipv6
Pass a `--enable-ipv6` option to a configure script. Enable support for an IPv6 protocol to allow a `libtirpc` library to issue RPC calls to IPv6 hosts.

It is recommended to enable this flag if the target system to be participating in IPv6-capable networks.

### kerberos
Pass a `--enable-gssapi` option to a configure script. Enable support of GSS-API (Generic Security Service Application Program Interface) for RPC calls authentication.

This flag should only be enabled if there is a need to authenticate RPC calls using a Kerberos v5 protocol.

### static-libs
Pass a `--enable-static` option to a configure script. Build and install a statically linked version of the `libtirpc` library.

This flag should only ever be enabled if there is an explicit need for the static library.
