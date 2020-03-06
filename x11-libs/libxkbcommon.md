# x11-libs/libxkbcommon

### doc
Pass the `-Denable-docs=true` option to the meson build script. Generate and API documentation from the source code annotation in an HTML format using the doxygen tool and install it into `/usr/share/docs/libxkbcommon-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Execute the `meson test` command after the main build is complete to run the test suite provided with the source code and check for regressions. This will extend a build time.

This flag should normally be disabled as it is mainly useful for maintainers, testers and developers.

### X
Pass the `-Denable-x11=true` option to the meson build script. Build and install a `libxkbcommon-x11` library and a `xkbcommon-x11.h` include file. Provide an ability to create and modify keymaps, e.g. change to special symbols when modifier key is pressed via an XKB X11 extension.

It is recommended to enable this flag if there is a need to run an X.Org server.
