# net-libs/libtirpc

### kerberos
Pass a `--enable-gssapi` option to a configure script. Enable support of GSS-API (Generic Security Service Application Program Interface) for RPC calls authentication.

This flag should only be enabled if there is a need to authenticate RPC calls using a Kerberos v5 protocol.

### split-usr
If the flag is enabled all produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Pass a `--enable-static` option to a configure script. Build and install a statically linked version of the `libtirpc` library.

This flag should only ever be enabled if there is an explicit need for the static library.
