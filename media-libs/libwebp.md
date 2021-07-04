# media-libs/libwebp

### gif
Pass the `--enable-gif` option to the configure script. Build and install a `gif2web` tool that converts a GIF image to a WebP image.

This flag can be safely disabled.

### jpeg
Pass the `--enable-jpeg` option to the configure script. Provide an ability to compress JPEG images into the WebP format using the `cwebp` tool.

It is safe to disable the flag.

### opengl
Pass the `--enable-gl` option to the configure script. Build and install the `vwebp` tool to decompresses a WebP file and display it in a window using the OpenGL API.

It is safe to disable the flag.

### png
Pass the `--enable-png` option to the configure script. Enable support to decompress WebP images into the PNG format using the `dwebp` tool and to compress PNG images into the WebP format using the `cwebp` tool.

It is safe to dsiable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked versions of the `libwebp`, `libwebpdecoder`, `libwebpmux` and the `libwebpdemux` libraries.

This flag should only be enabled if there is an explicit need for the static libraries.

### swap-16bit-csp
Pass the `--enable-swap-16bit-csp` option to the configure script. Enable byte swap for 16-bit colorspaces to convert between big endian and little endian byte order.

This flag should normally be disabled, at least on x86 architecture, but should be enabled for (rare) big-endian platforms.

### tiff
Pass the `--enable-tiff` option to the configure script. Provide an ability to compress TIFF images into the WebP format using the `cwebp` tool.

It is safe to disable the flag.
