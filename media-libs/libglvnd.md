# media-libs/libglvnd

### test
Run the `meson test` command (inside of the virtual Xvfb session if the `X` flag is enabled) after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend the overall build time.

This flag should normally be disabled, because aforementioned tests are mainly oriented towards developers, maintainers and testers.

### X
Pass the `-Dglx=enabled` and `-Dx11=enabled` options to the meson build script. Enable support for X11 (X Window System), build and install the `GLX_EXT_libglvnd` GLX extension, which allows `libGLX` to determine the number of the screen belonging to an arbitrary drawable XID (X window ID), and also the GL vendor to use for a given screen.

It is safe to disable this flag, but it should be enabled on systems with X11 server.
