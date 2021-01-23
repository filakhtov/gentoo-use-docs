# x11-libs/libXv

### doc
Install developer-specific man pages (such as `Xv`, `XvCreateImage`, `XvStopVideo`, etc) that include a list of symbols exported by the `libXv` library, their description and usage recommendation.

This flag should normally be disabled.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of the build. Build and install a statically linked version of the `libXv` library.

This flag should only be enabled if there is an explicit need for the static library.
