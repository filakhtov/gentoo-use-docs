# media-libs/tiff

### cxx
Pass the `--enable-cxx` option to the configure script. Build and install the `libtiffxx` library that currently only provides the `TiffStream` class to write and read TIFF files through a C++ stream interface.

This flag should be enabled if there is a need to use libtiff with C++ applications.

### jbig
Pass the `--enable-jbig` option to the configure script. Use the JBIG-KIT implementation of the JBIG1 lossless data compression standard (ITU-T T.82) to read and write ISO JBIG compressed TIFF images.

This flag should be normally disabled as JBIG1 is uncommon these days.

### jpeg
Pass the `--enable-jpeg` option to the configure script. Use the `libjpeg` library to enable IJG (Independent JPEG Group) JPEG (Joint Photographic Experts Group) lossless compression support for TIFF images.

It is safe to disable the flag, unless there is a need to access JPEG compressed TIFF images.

### lzma
Pass the `--enable-lzma` option to the configure script. Use the `liblzma` library to enable LZMA2 (Lempel–Ziv–Markov chain Algorithm) compression when reading and writing TIFF images.

It is safe to disable the flag, unless there is a need to access LZMA compressed TIFF images.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libtiff` (and `libtiffxx` if the `cxx` flag is enabled) libraries.

This flag should only be enabled if there is an explicit need for the static library.

### test
Execute the `make check` command after the main build is completed to run the regression test suite provided with the source code. This will extend the build time.

This flag should normally be disabled, because it is primarily oriented towards the Gentoo team, testers and developers.

### zlib
Pass the `--enable-zlib` option to the configure script. Use the `libz` library to enable Deflate compression algorithm for reading and writing TIFF images.

It is safe to disable the flag, unless there is a need to access Deflate compressed TIFF images.
