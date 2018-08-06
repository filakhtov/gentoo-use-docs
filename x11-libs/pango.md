# x11-libs/pango

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `Pango-1.0.gir`, `PangoCairo-1.0.gir`, `PangoFT2-1.0.gir` and, if the `X` flag is enabled, then `PangoXft-1.0.gir` GIR metadata files to provide dynamic bindings support for languages other than C using the GObject Introspection.

It is safe to disable this flag.

### test
Execute the `make check` command after the main build is completed. Run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is mainly orinted towards developers and testers.

### X
Pass the `--with-xft`, the `--x-includes=/usr/include` and the `--x-libraries=/usr/lib` options to the configure script. Build and install the `libpangoxft` library to enabled font handling and rendering with the Xft backend for displaying fonts on the X window system.

This flag should be enabled if the target system runs X Server without additional toolkit on top.
