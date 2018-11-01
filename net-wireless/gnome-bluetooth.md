# net-wireless/gnome-bluetooth

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `GnomeBluetooth-1.0.gir` GIR metadata file to provide dynamic bindings for the `libgnome-bluetooth` library to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### debug
Pass the `--enable-debug=yes` option to the configure script. Disable compiler optimizations, produce libraries and binaries with debugging symbols, enable additional runtime checks, and print extra debugging messages.

This flag should only be enabled for debugging purposes.
