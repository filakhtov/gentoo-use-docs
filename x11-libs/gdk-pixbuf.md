# x11-libs/gdk-pixbuf

### debug
Pass the `--enable-debug=yes` option to the configure script. Pass the `-g` debugging flag to the compiler at the build time to include debugging symbols into produced libraries. Enable additional runtime debugging code.

This flag should only be enabled for the debugging purposes.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate the `GdkPixbuf-2.0.gir` GIR metadatafile during a build time to provide dynamic bindings support for languages other than C via the GObject introspection middleware.

It is safe to disable the flag.

### jpeg
Pass the `--with-libjpeg` option to the configure script. Build and install the `libpixbufloader-jpeg` library - a progressive loader for JPEG image format.

This flag should be enabled to provide support for loading JPEG images via GDK-PixBuf library.

### jpeg2k
Pass the `--with-libjasper` option to the configure script. Build and install the `libpixbufloader-jasper` library - a progressive loader for JPEG2000 image format.

This flag should be enabled to provide support for loading JPEG2000 images via GDK-PixBuf library.

### test
Download a missing JPEG file necessary for running tests and copy it into the source tree. Execute a `make check` command to run a test suite provided with the source code after the main build is completed. This will extend a build time.

This flag should be normally disabled as it is primarily oriented to the developers and testers.

### tiff
Pass the `--with-libtiff` option to the configure script. Build and install the `libpixbufloader-tiff` library - a progressive loader for JPEG2000 image format.

This flag should be enabled to provide support for loading TIFF images via GDK-PixBuf library.

### X
Pass the `--with-x11` option to the configure script. Build and install the `libgdk_pixbuf_xlib` - a small library that lets Xlib-only applications use GdkPixbuf structures and render them to X drawables.

It is safe to disable the flag.
