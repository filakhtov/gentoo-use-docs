# x11-libs/libICE

### doc
Pass the `--enable-docs`, `--enable-specs` and the `--with-xmlto` options to the configure script. Build and install an additional documentation in HTML format to a `/usr/share/doc/libICE-<VERSION>/html` directory.

It is safe to disable this flag.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Define an `IPv6` macro that will be used by various system include files. Enable IPv6 protocol support for ICE connections via `tcp/` network ID.

The flag should only be enabled if the target system has to handle IPv6 connections via an ICE protocol.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install a statically linked a `libICE` library.

This flag should only be enabled if there is an explicit need for the static library.
