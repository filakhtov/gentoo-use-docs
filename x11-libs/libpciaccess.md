# x11-libs/libpciaccess

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install a statically linked a `libpciaccess` library.

This flag should be disabled, unless there is an explicit need to use the static library.

### zlib
Pass the `--with-zlib` option to the configure script. Use the `libz` library to support reading a Gzip compressed `pci.ids` database file.

This flag should be enabled if there is a need to use a compressed `pci.ids` file.
