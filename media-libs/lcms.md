# media-libs/lcms

### doc
Install additional developer and API documentation in the ODT (Open Document Type) format into the `/usr/share/doc/lcms-<VERSION>/` directory.

It is safe to disable the flag.

### jpeg
Pass a `--with-jpeg` option to a configure script. Build and install a `jpgicc` binary that provides an ability to apply an ICC (International Color Consortium) color profile to an image stored in a JPEG (Joint Photographic Experts Group) format for color correction.

It is safe to disable the flag.

### static-libs
Pass a enable `--enable-static` option to a configure script. Build and install a statically linked version of a `liblcms2` library.

This flag should only ever be enabled if there is a need for the static library.

### test
Execute a `make check` command after the main build is completed. Run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is primarily oriented towards developers and testers.

### threads
Pass a `--with-threads` option to a configure script. Build additional code that performs initialization and locking necessary for a `liblcms2` library to properly work with a multi-threaded application.

This flag should be enabled if there is a need to use the library with threaded apps.

### tiff
Pass a `--with-tiff` option to a configure script. Build and install a `tificc` tool that provides an ability to apply an ICC (International Color Consortium) color profile to an image stored in a TIFF (Tagged Image File Format) format for color correction.

It is safe to disable the flag.

### zlib
Only makes sense if the `tiff` flag is enabled. Pass the `--with-zlib` option to the configure script. Enable support for compressed TIFF images in `tificc` tool. See `tiff` flag for details.

This flag can be safely disabled.
