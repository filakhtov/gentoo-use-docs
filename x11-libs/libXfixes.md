# x11-libs/libXfixes

### doc
Install man pages that provide developer-specific information, i.e. description of the symbols provided by the library.

The flag should normally be disabled.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of the build. Build and install a statically linked version of the `libXfixes` library.

This flag should only be enabled if there is a need for the static library.
