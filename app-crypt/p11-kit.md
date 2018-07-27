# app-crypt/p11-kit

### asn1
Pass the `--with-libtasn1` option to the configure script. Use the `libtasn1` library to interact with certificates.

This flag should only be enabled together with `trust` flag. It does nothing on its own.

### debug
Pass the `--enable-debug` option to the configure script. Disable compiler optimizations and build binaries and libraries with debugging symbols. Output additional debugging information at runtime.

This flag should only be enabled if there is a need to debug a library itself or applications linked against it.

### libffi
Pass the `--with-libffi` option to the configure script. Use a `libffi` library to build closures for PKCS#11 module and allow sharing them between multiple callers in the same process.

It is recommended to enable this module.

### trust
Pass the `--enable-trust-module` and the `--with=trust-paths=/etc/ssl/certs/ca-certificates.crt` options to the configure script. Build and install the `p11-kit-trust` library - a trust module that provides system certificate anchors, blacklists and other trust policy to crypto libraries and applications.

This flag can be safely disabled, however doing so will drastically limit library abilities.
