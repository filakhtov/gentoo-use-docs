# x11-libs/libxcb

### doc
Pass the `--enable-devel-docs` option to the configure script. Extract an API documentation in an HTML format using a Doxygen generator and install it into a `/usr/share/doc/libxcb-<VERSION>/html` directory.

It is safe to disable this flag.

### selinux
Pass the `--enable-selinux` option to the configure script. Build and install a `libxcb-xselinux` library. Provide an API to access an XSELinux (SELinux X-Windows implementation) for fine grained access control over the X-server objects (aka resources) using an X-Windows extention acting as the object manager.

It is recommended to toggle this flag system-wide, e.g. as part of the SELinux-enabled portage profile.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install statically linked libraries, e.g. a `libxcb-xinput`, `libxcb-render`, `libxcb-composite` and so forth.

This flag should normally be disabled, unless there is an explicit need for static libraries.

### test
Run a `make check` command when the main build is finished. Build and execute a test suite provided with a source code. This will extend a build time.

This flag should usually be disabled, as it is only useful for the Gentoo team, developers or testers.

### xkb
This flag does nothing starting from version `1.14` and should be disabled.
