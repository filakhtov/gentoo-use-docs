# x11-libs/libXfont2

### bzip2
Pass the `--with-bzip2` option to the configure script. Use the `libbz2` library to support BZip2 compressed bitmap fonts.

This flag should be enabled if there is a need for an X server to load BZip2 compressed fonts.

### doc
Pass the `--enable-devel-docs` and the `--with-xmlto` options to the configure script. Generate additional developer documentation using the DocBook and xmlto utils and install it into the `/usr/share/doc/libXfont2-<VERSION>` directory.

It is safe to disable the flag.

### truetype
Pass the `--enable-freetype` option to the configure script. Use the FreeType library to handle scalable font formats including OpenType, FreeType, and PostScript formats. Can also be used to handle bdf & bitmap pcf font formats.

This flag should be enabled to provide support for wider range of font formats.
