# x11-libs/libSM

### doc
Pass the `--enable-docs` and the `--with-xmlto` options to the configure script. Generate and install additional documentation into a `/usr/share/doc/libSM-<VERSION>` directory.

This flag can be safely disabled.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable support to generate an ID for clients connected over an IPv6 protocol based on a hostname or an IP addresses. This flag does nothing if a `uuid` flag is enabled.

It is recommended to disable this flag. It should only be enabled if a `libuuid` is not available and there are network clients that connect over IPv6.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install a statically linked a `libSM` library.

This flag should be disabled, unless there is an explicit need to use the static library.

### uuid
Pass the `--with-libuuid` option to the configure script. When disabled, export an `ac_cv_func_uuid_create=no` variable for the configure script. Use a `UUID` to generate a globally unique client ID instead of using a `gethostbyname()` call that might result in DNS timeout and failure.

This flag should be enabled if there is a need to connect from the remote network clients. It is safe to disable otherwise.
