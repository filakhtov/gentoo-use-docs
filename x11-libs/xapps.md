# x11-libs/xapps

### introspection
Pass a `--enable-introspection` option to a configure script. Generate and install a `XApp-1.0.gir` GIR metadata file to provide dynamic bindings for a `libxapp` library to languages other than C using a GObject Introspection framework.

It is safe to disable the flag.

### static-libs
Pass a `--enable-static` option to a configure script. Build and install a statically linked version of a `libxapp` library.

This flag should only be enabled if there is an explicit need for the static library.
