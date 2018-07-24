# x11-libs/libXt

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install a statically linked version of a `libXt` library.

This flag should only be enabled if there is a need for the static library.

### test
Execute a `make check` option after the main build is completed. Execute a test suite provided with the source code. This will extend a build time.

The flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
