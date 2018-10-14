# media-libs/libdvdread

### css
Pass the `--enable-libdvdcss` option to the configure script. Link against the `libdvdcss` library to provide an ability to access and unscramble DVD disks encrypted with the CSS (Content Scramble System) - a digital rights management (DRM) and encryption system employed on many commercially produced DVD-Video discs.

This flag should be enabled if there is a need to use CSS-protected DVDs.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libdvdread` library.

This flag should only be enabled if there is an explicit need for the static library.
