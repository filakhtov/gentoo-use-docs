# x11-libs/libXcomposite

### doc
Pass the `--with-xmlto` option to the configure script. Use the `xmlto` tool to regenerate the documentation from the soruce code instead of installing a prebuilt one.

This flag should normally be disabled.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install a statically linked version of the `libXcomposite` library.

This flag should only be enabled if there is a need for the static library.
