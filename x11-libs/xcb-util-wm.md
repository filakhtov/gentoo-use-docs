# x11-libs/xcb-util-wm

### doc
Pass a `--with-doxygen` option to a configure script. Generate and API documentation in an HTML format using a doxygen tool and install it into `/usr/share/docs/xcb-util-wm-<VERSION>/html` directory.

It is safe to disable the flag.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install a statically linked version of a `libxcb-icccm` and a `libxcb-ewmh` libraries.

This flag should only be enabled if there is an explicit need for the static libraries.

### test
Execute a `make check` option after the main build is completed. Execute a test suite provided with the source code. This will extend a build time.

The flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
