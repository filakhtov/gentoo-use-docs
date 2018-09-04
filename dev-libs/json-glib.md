# dev-libs/json-glib

### debug
Pass a `--enable-debug=yes` option to a configure script (`--enable-debug=minimum` when disabled). Build and install a library with debugging symbols included and produce additional runtime debugging output.

This flag should only be enabled for debugging purposes.

### introspection
Pass a `--enable-introspection` option to a configure script. Generate and install a `Json-1.0.gir` GIR metadata file to provide dynamic bindings for a `libjson-glib` library to languages other than C using a GObject Introspection infrastructure.

It is safe to disable the flag.
