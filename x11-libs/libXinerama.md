# x11-libs/libXinerama

### doc
Install the developer-centric man pages for the `libXinerama` library that lists all the symbols exported by the library and provides their description and usage details.

This flag should normally be disabled.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables, and a `-Bdirect` option from an `LDFLAGS` variable for the duration of a build. Build and install a statically linked version of the `libXinerama` library.

This flag should normally be disabled, unless there is an explicit need for the static library.
