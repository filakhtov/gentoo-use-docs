# x11-libs/gdk-pixbuf

### gtk-doc
Pass the `-Dgtk_doc=true` option to the Meson build script. Use the Gtk-Doc tool to extract annotations from the source code to generate developer documentation in the HTML format and install it into the `/usr/share/gtk-doc/html/gdk-pixbuf` directory.

This flag should normally be disabled.

### introspection
Pass the `-Dintrospection=enabled` (`disabled` if the flag is disabled) option to the Meson build script. Generate the `GdkPixbuf-2.0.gir` GIR metadatafile during a build time to provide dynamic bindings support for languages other than C via the GObject introspection middleware.

It is safe to disable the flag.

### jpeg
Pass the `-Djpeg=enabled` (`disabled` when the flag is disabled) option to the Meson build script. Build and install the `libpixbufloader-jpeg` library - a progressive loader for JPEG image format.

This flag should be enabled to provide support for loading JPEG images via GDK-PixBuf library.

### test
Pass the `-Dtests=true` (`false` when the flag is disabled) option to the Meson bulid script. Build a test suite provided with the source code and execute the `meson test` command after the main build is completed to run the suite and check for regressions.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.

### tiff
Pass the `-Dtiff=enabled` (`disabled` when the flag is disabled) option to the Meson build script. Build and install the `libpixbufloader-tiff` library - a progressive loader for TIFF image format.

This flag should be enabled to provide support for loading TIFF images via GDK-PixBuf library.
