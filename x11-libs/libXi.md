# x11-libs/libXi

### doc
Pass the `--enable-specs`, the `--with-xmlto` and the `--with-asciidoc` options to the configure script. Generate and install additional documentation into the `/usr/share/doc/libXi-<VERSION>` directory using AsciiDoc and DocBook tools.

It is safe to disable the flag.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of the build. Build and install a statically linked version of the `libXi` library.

This flag should only be enabled if there is a need for the static library.
