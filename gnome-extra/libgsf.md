# gnome-extra/libgsf

### bzip2
Pass the `--with-bz2` option to the configure script. Enable support for Bzip2 compressed data, both for reading and writing.

This flag can be safely disabled.

### gtk
Pass the `--with-gdk-pixbuf` option to the configure script. Use the `gdk-pixbuf` library to generate thumbnail images, instead of resorting back to calling the external `convert` binary provided by the [media-gfx/imagemagick](../media-gfx/imagemagick.md) package.

It is recommended to enable this flag, especially on GTK+-based desktop environments.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `Gsf-1.gir` GIR metadat file to provide dynamic bindings for the `libgsf` library to languages other than C using the GObject Introspection framework.

This flag can be safely disabled.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily targeted towards the developers, maintainers and testers.
