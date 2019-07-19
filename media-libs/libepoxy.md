# media-libs/libepoxy

### egl
Pass in the `-Degl=yes` option to the configure script. Enable support for the EGL stack and allow relevant symbols to be automatically loaded on their first use.

This flag should normally be disabled, unless there is a need to use the EGL stack, e.g. under Wayland.

### test
Execute the `ninja test` command to run a test suite provided with the source code. This will extend a build time.

It is recommended to disable the flag as it is mainly useful for the Gentoo team, developers or testers.

### X
Pass the `-Dglx=yes` and the `-Dx11=true` options to the `meson` build tool. Provide an ability to dynamically load GLX (an OpenGL extension to the X Window System) functions first time a call to such function is made.

This flag should be enabled if the target system is running X Server.
