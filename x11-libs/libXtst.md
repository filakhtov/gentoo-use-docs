# x11-libs/libXtst

### doc
This flag is inherited from the parent eclass `xorg-2` and is not doing anything. It should be disabled.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of the build. Build and install a statically linked version of the `libXtst` library.

This flag should only be enabled if there is a need for the static library.
