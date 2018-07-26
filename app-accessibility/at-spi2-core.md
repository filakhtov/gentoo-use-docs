# app-accessibility/at-spi2-core

### introspection
Pass the `--enable-introspection` option to the configure script. Generate GIR metadata `Atspi-2.0.gir` file during a build time to provide dynamic bindings support for languages other than C.

It is safe to disable the flag.

### X
Pass the `--enable-x11` option to the configure script. Provide support for X-specific device event controller support.

This flag should be enabled if there is a need for accessibility support for X.Org display server.
