# x11-libs/gdk-pixbuf

### gtk-doc
Pass the `-Ddocs=true` (`false` when the flag is disabled) option to the meson configure command. Use the Gtk-Doc tool to extract source code annotations and generate the HTML documentation that will be installed into the `/usr/share/gtk-doc/html/gdk-pixbuf` directory.

This flag should normally be disabled, because documentation is primarily oriented towards developers.

### introspection
Pass the `-Dgir=true` (`false` if the flag is disabled) option to the meson configure command. Generate the `GdkPixbuf-2.0.gir` GIR metadatafile during a build time to provide dynamic bindings support for languages other than C via the GObject introspection middleware.

It is safe to disable the flag.

### jpeg
Pass the `-Djpeg=true` (`false` when the flag is disabled) option to the meson configure command. Build and install the `libpixbufloader-jpeg` library - a progressive loader for JPEG image format.

This flag should be enabled to provide support for loading JPEG images via GDK-PixBuf library.

### tiff
Pass the `-Dtiff=true` (`false` when the flag is disabled) option to the meson configure command. Build and install the `libpixbufloader-tiff` library - a progressive loader for TIFF image format.

This flag should be enabled to provide support for loading TIFF images via GDK-PixBuf library.

### X
Pass the `-Dx11=true` (`false` if the flag is disabled) option to the configure script. Build and install the `libgdk_pixbuf_xlib` - a small library that lets Xlib-only applications use GdkPixbuf structures and render them to X drawables.

It is safe to disable the flag.
