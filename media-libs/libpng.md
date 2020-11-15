# media-libs/libpng

### apng
Apply a patch to enable support for the APNG (Animated Portable Network Graphics) image format. Animated PNG files work similarly to animated GIF files, while supporting 24-bit images and 8-bit transparency not available for GIFs. This format is also backwards compatible with non-animated PNG files.

It is safe to disable this flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked verion of the `libpng` library.

This flag should only be enabled if there is a need for the static library.
