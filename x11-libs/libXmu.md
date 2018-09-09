# x11-libs/libXmu

### doc
Pass the `--enable-docs` and the `--with-xmlto` options to the configure script. Use the xmlto and DocBook tools to generate additional documentation and install it into the `/usr/share/doc/libXmu-<VERSION>` directory.

It is safe to disable the flag.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Define the `IPv6` macro used by system include files to enable IPv6 protocol support for the networking code. Note, however that this library is not entirely IPv6 compatible, see the [Freedesktop bug #7611](https://bugs.freedesktop.org/show_bug.cgi?id=7611) for details.

This flag should be enabled if there is a need to run networked X Server over the IPv6 protocol.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install a statically linked version of the `libXmu` and the `libXmuu` libraries.

This flag should only be enabled if there is a need for the static library.
