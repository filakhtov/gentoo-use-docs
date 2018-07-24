# x11-libs/libXdmcp

### doc
Pass the `--enable-docs` and the `--with-xmlto` options to the configure script. Build and install an additional documentation into the `/usr/share/doc/libXdmcp-<VERSION>` directory, including an API documentation and protocol description.

It is safe to disable the flag.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install a statically linked version of the `libXdmcp` library.

This flag should only be enabled if there is a need for the static library.
