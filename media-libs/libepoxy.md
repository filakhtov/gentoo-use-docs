# media-libs/libepoxy

### egl
Pass in the `-Degl=yes` option to the configure script. Enable support for the EGL stack and allow relevant symbols to be automatically loaded on their first use.

This flag should normally be disabled, unless there is a need to use the EGL stack, e.g. under Wayland.

### test
Start a new Xvfb session (Virtual X server environment) and execute the `ninja test` command inside of it after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

It is recommended to disable the flag as it is mainly useful for the Gentoo team, developers or testers.

### X
Pass the `-Dglx=yes` and the `-Dx11=true` options to the `meson` build tool. Provide an ability to dynamically load GLX (an OpenGL extension to the X Window System) functions first time a call to such function is made.

This flag should be enabled if the target system is running X Server.
