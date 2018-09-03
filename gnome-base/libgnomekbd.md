# gnome-base/libgnomekbd

### introspection
Pass a `--enable-introspection` option to a configure script. Generate a `Gkbd-3.0.gir` GIR metadata file to provide dynamic bindings for a `libgnomekbd` and a `libgnomekbdui` libraries to languages other than C using the GObject Introspection.

It is safe to disable the flag.

### test
Pass a `--enable-tests` option to a configure script. Build test code during the main build process and execute a `make check` command once it is completed to run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is mainly used by the Gentoo team, testers or developers.
