# x11-libs/gdk-pixbuf

### introspection
Pass the `-Dintrospection=enabled` (`disabled` if the flag is disabled) option to the meson configure command. Generate the `GdkPixbuf-2.0.gir` GIR metadatafile during a build time to provide dynamic bindings support for languages other than C via the GObject introspection middleware.

It is safe to disable the flag.

### jpeg
Pass the `-Djpeg=true` (`false` when the flag is disabled) option to the meson configure command. Build and install the `libpixbufloader-jpeg` library - a progressive loader for JPEG image format.

This flag should be enabled to provide support for loading JPEG images via GDK-PixBuf library.

### tiff
Pass the `-Dtiff=true` (`false` when the flag is disabled) option to the meson configure command. Build and install the `libpixbufloader-tiff` library - a progressive loader for TIFF image format.

This flag should be enabled to provide support for loading TIFF images via GDK-PixBuf library.
