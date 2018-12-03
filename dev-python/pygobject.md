# dev-python/pygobject

### cairo
Pass the `--enable-cairo` option to the configure script. Provide special cairo integration through the Pycairo module despite cairo library itself not being a GObject based. Provide an ability to load Cairo interface using the `gi.require_foreign("cairo")` call.

This flag should only be enabled if there is a need to use Python GObject bindings for the Cairo library.

### examples
Install additional example files into the `/usr/share/doc/pygobject-<VERSION>/examples` directory. This includes a demo Cairo project written in Python and based on the C code from the Cairo library itself.

It is safe to disable the flag.

### libffi
Pass the `--with-ffi` option to the configure script. Use the `libffi` library to provide an ability to directly call into underlying C libraries.

This flag should normally be enabled, because Glib an GObject Introspection are dependent on `libffi` anyway.

### test
Prepare an environment, start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is primarily used by the Gentoo team, developers and testers.
