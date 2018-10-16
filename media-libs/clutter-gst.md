# media-libs/clutter-gst

### debug
Pass the `--enable-debug=yes` option (`minimum` when disabled) to the configure script. Build the `libclutter-gst` library with debugging symbols included and produce additional debugging messages at runtime.

This flag should only be enabled for the debugging purposes.

### examples
Install additional source code written in C and JavaScript languages into the `/usr/share/doc/clutter-gst-<VERSION>` directory, that demonstrates how to use `libclutter-gst` for different use cases, including the simple app showing webcams dynamically connected to the computer, quick little demo moving around pieces of a video stream, a small example switching between 2 video streams on move events, etc.

It is safe to disable the flag.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `ClutterGst-1.0.gir` GIR metadata file to provide dynamic bindings for the `libclutter-gst` library to languages other than C using the GObject Introspection framework.

The flag can be safely disabled.

### udev
Pass the `--enable-udev` option to the configure script. Use the `libgudev` library to obtain a list of cameras, properly handle dynamic connection and disconnection and query information about them.

This flag should be enabled if there is a need to access cameras via this library.

### X
Make sure that an `X` USE flag is synchronized between this package and [media-libs/clutter](../media-libs/clutter.md) package.

This flag should normally be enabled, unless there is a need to use the `libclutter-gst` library outside of the X Server, e.g. with Wayland.
