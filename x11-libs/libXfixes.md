# x11-libs/libXfixes

### doc
This flag does nothing. It is inherited from the `xorg-2` eclass, but is not used by the ebuild itself.

The flag should be disabled.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of the build. Build and install a statically linked version of the `libXfixes` library.

This flag should only be enabled if there is a need for the static library.
