# media-libs/lcms

### doc
Install additional developer and API documentation in the PDF format into the `/usr/share/doc/lcms-<VERSION>/` directory.

It is safe to disable the flag.

### jpeg
Pass the `-Djpeg=enabled` option to the meson build script. Build and install a `jpgicc` binary that provides an ability to apply an ICC (International Color Consortium) color profile to an image stored in a JPEG (Joint Photographic Experts Group) format for color correction.

It is safe to disable the flag.

### static-libs
Pass the `-Ddefault_library=both` (instead of `shared`) option to the meson build script. Build and install a statically linked version of a `liblcms2` library.

This flag should only ever be enabled if there is a need for the static library.

### tiff
Pass the `-Dtiff=enabled` option to the meson build script. Build and install a `tificc` tool that provides an ability to apply an ICC (International Color Consortium) color profile to an image stored in a TIFF (Tagged Image File Format) format for color correction.

It is safe to disable the flag.
