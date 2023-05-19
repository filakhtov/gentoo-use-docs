# media-gfx/gthumb

### cdr
Pass the `-Dlibbrasero=true` option to the meson build script. Build and install an export plugin that uses the `libbrasero` library to provide an ability to write images and photos onto the CD/DVD disks or create ISO images.

It is safe to disable the flag.

### colord
Pass the `-Dcolord=true` and `-Dlcms2=true` options to the meson build script. Use the colord service to make ICC color profiles to properly work when running on the Wayland display server.

This flag should be enabled when target system runs the Wayland display server.

### exif
Pass the `-Dexiv2=true` option to the Meson build script. Build and install the `EXIF, IPTC, XMP support` plugin that uses the Exiv2 library to read and write EXIF, IPTC and XMP metadata. Also provide an ability for importer and comments plugins to access file metadata.

It is recommended to enable this flag if there is a need to deal with photos.

### gstreamer
Pass the `-Dgstreamer=true` option to the Meson build script. Build and install the "Audio/Video support" plugin that uses the GStreamer framework to provide an ability to play audio and video files from gThumb. GStreamer is also integrated with slideshow plugin (see the `slideshow` flag).

It is safe to disable the flag unless there is a need to play media files.

### heif
Pass the `-Dlibheif=true` option to the Meson build script. Use the `libheif` library to enable support for HEIF (High Efficiency Image File Format) images (including the Apple’s `.heic`).

This flag can be safely disabled, if there is no need to open HEIF images with gThumb.

### http
This flag only works together with the `json` and `webkit` flags. Pass the `-Dwebservices=true` option to the configure script. Use the `libsoup` library to handle HTTP(S) connections for various web service plugins, such as Upload to Facebook, Flickr, Picasa, etc.

This flag can be safely disabled if there is no need to upload images to web services.

### jpegxl
Pass the `-Dlibjxl=true` option to the Meson build script. Use the `libjxl` library to enable support for JPEG XL (`.jxl`) - the next generation image coding standard.

It is safe to disable this flag unless there is a need to open JXL images in gThumb.

### keyring
Only makes sense if the `http`, `webkit` and `json` flags are enabled. Pass the `-Dlibsecret=true` option to the configure script. Provide an ability to read credentials from and save them to a system keyring using the `libsecret` library. This functionality is used by the oAuth authentication flow to upload images via various web service plugins, e.g. 23hq.com, Facebook, Flickr, etc.

This flag can be safely disabled if there is no need to use web services or store credentials in a keyring.

### lcms
Pass the `-Dlcms2=true` option to the Meson build script. Use the Little CMS color engine to provide an ability to handle ICC color profiles and try to reproduce image colors more accurately when viewing an image (e.g. convert colors from image color profile into the display color profile).

It is safe to disable this flag if there is no need to handle color profiles.

### raw
Pass the `-Dlibraw=true` option to the Meson build script. Use the `libraw` library directly, instead of using the code of the `dcraw` tool for reading RAW image format.

It is recommended to enable this flag as `libraw` based on the code of the `dcraw` with additional improvements.

### slideshow
Pass the `-Dclutter=true` option to the Meson build script. Build and install the slideshow plugin that uses the `libclutter` library to present images as a slide show. When the `gstreamer` flag is enabled, also provide an ability to play videos from beginning to end before switching to a next source during a slideshow.

The flag can be safely disabled if there is no need for slideshow functionality.

### svg
Pass the `-Dlibrsvg=true` option to the Meson build script. Use the `librsvg` library to enable full-featured SVG image support, i.e. an ability to perform high-quality zooming of vectorized data, instead of showing embedded PNG preview (thumbnail).

This flag should be enabled if there is a need to view SVG images.

### tiff
Pass the `-Dlibtiff=true` option to the Meson build script. Use the `libtiff` library to provide advanced support for TIFF files, e.g. not only displaying the thumbnail, but actually showing full-size image, zooming, as well as saving and converting images into the TIFF format.

This flag should be enabled if there is a need to handle TIFF files.

### webp
Pass the `-Dlibwebp=true` option to the Meson build script. Use the `libwebp` library to provide an ability to display images in the WebP format and also save (or convert) into this format.

This flag should be enabled if there is a need to view, convert or save WebP images.
