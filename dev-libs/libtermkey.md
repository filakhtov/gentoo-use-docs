# dev-libs/libtermkey

### demos
By default a number of demo programs is built and installed: `demo`, `demo-async` and `demo-glib`. These programs demonstrate the capabilities of the `libtermkey` library and show how to build a simple application, asynchronous one that uses polling and how to use the library in the GLib-based application. When the flag is disabled, patch the `Makefile` to prevent building and installing these demo programs.

It is safe to disable this flag.

### static-libs
By default, a statically linked version of the `libtermkey` is built and installed into the system. When this flag is disabled, the static library will not be installed.

This flag should only be enabled if there is a need for the static library.
