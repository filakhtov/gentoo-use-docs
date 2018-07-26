# x11-libs/libXext

### doc
Pass the `--enable-spec` and the `--enable-xmlto` options to the configure script. Use DocBook XML to generate and install additional documentation into the `/usr/share/doc/libXext-<VERSION>` directory.

It is safe to disable the flag.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from an `LDFLAGS` variable for a duration of the build. Build and install a statically linked version of the `libXext` library.

This flag should only be enabled if there is a need for the static library.
