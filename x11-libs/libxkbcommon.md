# x11-libs/libxkbcommon

### doc
Pass the `--with-doxygen` option to the configure script. Generate and API documentation in an HTML format using a doxygen tool and install it into `/usr/share/docs/libxkbcommon-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Execute a `make check` command after the main build is complete. Run test cases provided with a source code. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.

### X
Does nothing when enabled (because X11 support is enabled by default). If disabled, pass `--disable-x11` option to the configure script. Build and install a `libxkbcommon-x11` library and a `xkbcommon-x11.h` include file. Provide an ability to create and modify keymaps, e.g. change to special symbols when modifier key is pressed via an XKB X11 extension.

It is recommended to enable this flag if there is a need to run an X.Org server.
