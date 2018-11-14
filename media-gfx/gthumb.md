# media-gfx/gthumb

### cdr
Pass the `--enable-libbrasero` option to the configure script. Build and install an export plugin that uses the `libbrasero` library to provide an ability to write images and photos onto the CD/DVD disks or create ISO images.

It is safe to disable the flag.

### debug
Pass the `--enable-debug` option to the configure script. Disable compiler optimizations and build binaries and libraries with debugging symbols. Enable output of the debugging messages to the stderr at runtime.

This flag should only be enabled if there is a need to debug the program.

### exif
Pass the `--enable-exiv2` option to the configure script. Build and install the `EXIF, IPTC, XMP support` plugin that uses the Exiv2 library to read and write EXIF, IPTC and XMP metadata. Also provide an ability for importer and comments plugins to access file metadata.

It is recommended to enable this flag if there is a need to deal with photos.

### gnome-keyring
Only makes sense if the `http`, `webkit` and `json` flags are enabled. Pass the `--enable-libsecret` option to the configure script. Provide an ability to read credentials from and save them to a system keyring using the `libsecret` library. This functionality is used by the oAuth authentication flow to upload images via various web service plugins, e.g. 23hq.com, Facebook, Flickr, etc.

This flag can be safely disabled if there is no need to use web services or store credentials in a keyring.

### gstreamer
Pass the `--enable-gstreamer` option to the configure script. Build and install the "Audio/Video support" plugin that uses the GStreamer framework to provide an ability to play audio and video files from gThumb. GStreamer is also integrated with slideshow plugin (see the `slideshow` flag).

It is safe to disable the flag unless there is a need to play media files.

### http
This flag only works together with the `json` and `webkit` flags. Pass the `--enable-libsoup` option to the configure script. Use the `libsoup` library to handle HTTP(S) connections for various web service plugins, such as Upload to Facebook, Flickr, Picasa, etc.

This flag can be safely disabled if there is no need to upload images to web services.

### jpeg
Pass the `--enable-jpeg` option to the configure script. Build and install advanced JPEG support plugin that uses the `libjpeg` library to provide an ability to save or convert images into the JPEG format.

It is recommended to enable this flag if there is a need to deal with JPEG images, especially photos.

### json
This flag only works together with the `http` and `webkit` flags. Pass the `--enable-libjson-glib` option to the configure script. Use the JSON-Glib library to handle JSON data when communicating for various web services and is a required dependency for various web upload plugins, such as upload to Facebook, Flickr, etc.

This flag can be safely disabled if there is no need to use any of the web service plugins.

### lcms
Pass the `--enable-lcms2` option to the configure script. Use the Little CMS color engine to provide an ability to handle ICC color profiles and try to reproduce image colors more accurately when viewing an image (e.g. convert colors from image color profile into the display color profile).

It is safe to disable this flag if there is no need to handle color profiles.

### raw
Pass the `--enable-libraw` option to the configure script. Use the `libraw` library directly, instead of using the code of the `dcraw` tool for reading RAW image format.

It is recommended to enable this flag as `libraw` based on the code of the `dcraw` with additional improvements.

### slideshow
Pass the `--enable-clutter` option to the configure script. Build and install the slideshow plugin that uses the `libclutter` library to present images as a slide show. When the `gstreamer` flag is enabled, also provide an ability to play videos from beginning to end before switching to a next source during a slideshow.

The flag can be safely disabled if there is no need for slideshow functionality.

### svg
Pass the `--enable-librsvg` option to the configure script. Use the `librsvg` library to enable full-featured SVG image support, i.e. an ability to perform high-quality zooming of vectorized data, instead of showing embedded PNG preview (thumbnail).

This flag should be enabled if there is a need to view SVG images.

### test
Pass the `--enable-test-suite` option to the configure script. Build the the test suite provide with the source code and execute the `make check` command to run regression tests when the main build is completed. This will extend a build time.

This flag should be normally disabled as these tests are primarily used by the Gentoo team, developers or testers.

### tiff
Pass the `--enable-tiff` option to the configure script. Use the `libtiff` library to provide advanced support for TIFF files, e.g. not only displaying the thumbnail, but actually showing full-size image, zooming, as well as saving and converting images into the TIFF format.

This flag should be enabled if there is a need to handle TIFF files.

### webkit
Only works together with the `http` and `json` flags. Pass the `--enable-webkit2` option to the configure script. Use the GTK+ port of the WebKit2 engine to handle authentication flows (e.g. oAuth) for uploading images to various web services, e.g. Facebook, Flickr, etc.

It is safe to disable the flag if there is no need to upload images to web services.

### webp
Pass the `--enable-libwebp` option to the configure script. Use the `libwebp` library to provide an ability to display images in the WebP format and also save (or convert) into this format.

This flag should be enabled if there is a need to view, convert or save WebP images.
