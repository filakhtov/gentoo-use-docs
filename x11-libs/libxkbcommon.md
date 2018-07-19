# x11-libs/libxkbcommon

### doc
Pass the `--with-doxygen` option to the configure script. Generate and API documentation in an HTML format using a doxygen tool and install it into `/usr/share/docs/libxkbcommon-<VERSION>/html` directory.

It is safe to disable the flag.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables, and a `-Bdirect` option from an `LDFLAGS` variable for the duration of a build. Build and install a statically linked `libxkbcommon` (and also a `libxkbcommon-x11` if an `X` flag is enabled) library.

This flag should normally be disabled, unless there is an explicit need for the static library.

### test
Execute a `make check` command after the main build is complete. Run test cases provided with a source code. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.

### X
Does nothing when enabled (because X11 support is enabled by default). If disabled, pass `--disable-x11` option to the configure script. Build and install a `libxkbcommon-x11` library and a `xkbcommon-x11.h` include file. Provide an ability to create and modify keymaps, e.g. change to special symbols when modifier key is pressed via an XKB X11 extension.

It is recommended to enable this flag if there is a need to run an X.Org server.
