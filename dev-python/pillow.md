# dev-python/pillow

### doc
Execute the `make html` command from the `docs` source subdirectory to generate additional documentation in the HTML format and install it into the `/usr/share/doc/pillow-<VERSION>/html` directory.

It is safe to disable the flag.

### examples
Install additional example files into the `/usr/share/doc/pillow-<VERSION>/examples` directory. Examples show how to perform image adjustments like sharpness, brightness and contrast manipulation, how to split animation into a number of frame files, convert a sequence of GIF images into an animation, image file conversion, etc.

This flag can be safely disabled.

### imagequant
Pass the `--enable-imagequant` option to the configure script. Use the `libimagequant` to provide higher quality color quantization option when converting RGBA images to 8-bit indexed-color (palette) images.

This flag should be enabled to achieve smaller image sizes and more accurate color matching.

### jpeg
Pass the `--enable-jpeg` option to the configure script. Use the `libjpeg` library to provide an ability to read JPEG (Joint Photographic Experts Group), JFIF (JPEG File Interchange Format), and Adobe JPEG files containing L, RGB (Red-Green-Blue), or CMYK (Cyan-Magenta-Yellow-Key) data and write standard and progressive JFIF files.

This flag should be enabled if there is a need to handle JPEG images.

### jpeg2k
Pass the `--enable-jpeg2000` option to the configure script. Use the `libopenjpeg` library to provide an ability to read and writes JPEG 2000 files containing L, LA, RGB or RGBA data, and also read files containing YCbCr data, which is converted into RGB or RGBA on read depending on whether or not there is an alpha channel. Provide support for JPEG 2000 raw codestreams (`.j2k` files), as well as boxed JPEG 2000 files (`.j2p` or `.jpx` files).

This flag should be enabled if there is a need to handle JPEG 2000 images.

### lcms
Pass the `--enable-lcms` option to the configure script. Build and install the `PIL.ImageCms` Python module to provide color profile management support using the LittleCMS2 color management engine, based on Kevin Cazabon’s PyCMS library.

This flag should be enabled if there is a need to work with color profiles.

### test
Execute the `selftest.py --installed` command, then start the virtual Xvfb session and execute the `nosetests -vx Tests/test_*.py` command after the main build is completed. Run the test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is mainly useful for developers, tester or the Gentoo team.

### tiff
Pass the `--enable-tiff` option to the configure script. Use the `libtiff` library to allow PIL to read and write compressed TIFF files. If disabled, PIL will always write uncompressed files.

This flag should be enabled if there is a need to manage compressed TIFF images.

### tk
Make sure that the `tk` flag is enabled for the [dev-lang/python](../dev-lang/python.md) package. Build and install the `PIL.ImageTk` Python module - an ImageTk module that contains support to create and modify Tkinter BitmapImage and PhotoImage objects from PIL images.

This flag should be enabled if there is a need to produce native images for the Tk GUI toolkit.

### truetype
Pass the `--enable-freetype` option to the configure script. Build and install the `PIL.ImageFont` Python module that uses the FreeType library and provides a class to store bitmap fonts that are used with the `PIL.ImageDraw.Draw.text()` method. Enable support for TrueType and OpenType fonts (as well as other font formats supported by the FreeType library).

This flag should be enabled if there is a need to draw text.

### webp
Pass the `--enable-webp` and the `--enable-webpmux` options to the configure script. Use the `libwebp` library to provide support to read and write images in the WebP format and an ability to create animated WebP files from non-animated WebP images, extract frames from animated WebP images.

This flag should be enabled if there is a need to work with WebP images.

### xcb
Pass the `--enable-xcb` option to the configure script. Use the XCB library to provide an ability to capture screenshots using the `ImageGrab.grab()` method.

It is safe to disable this flag.

### zlib
Pass the `--enable-zlib` flag to the configure script. Use the `libz` library to provides support to read and write compressed PNG (Portable Network Graphics) files.

This flag should be enabled if there is a need to work with compressed PNG files.
