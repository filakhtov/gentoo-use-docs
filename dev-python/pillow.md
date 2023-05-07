# dev-python/pillow

### debug
Add the `-UNDEBUG` option to the `CPPFLAGS` environment variable for the duration of the build. Build the package with debugging symbols and some additional debugging routines enabled.

This flag should normally be disabled.

### examples
Install additional example files into the `/usr/share/doc/pillow-<VERSION>/examples` directory. Examples show how to perform image adjustments like sharpness, brightness and contrast manipulation, how to split animation into a number of frame files, convert a sequence of GIF images into an animation, image file conversion, etc.

This flag can be safely disabled.

### imagequant
Write the `enable_imagequant = True` option to the `setup.cfg` build configuration file. Use the `libimagequant` to provide higher quality color quantization option when converting RGBA images to 8-bit indexed-color (palette) images.

This flag should be enabled to achieve smaller image sizes and more accurate color matching.

### jpeg
Write the `enable_jpeg = True` option to the `setup.cfg` build configuration file. Use the `libjpeg` library to provide an ability to read JPEG (Joint Photographic Experts Group), JFIF (JPEG File Interchange Format), and Adobe JPEG files containing L, RGB (Red-Green-Blue), or CMYK (Cyan-Magenta-Yellow-Key) data and write standard and progressive JFIF files.

This flag should be enabled if there is a need to handle JPEG images.

### jpeg2k
Write the `enable_jpeg2000 = True` option to the `setup.cfg` build configuration file. Use the `libopenjpeg` library to provide an ability to read and writes JPEG 2000 files containing L, LA, RGB or RGBA data, and also read files containing YCbCr data, which is converted into RGB or RGBA on read depending on whether or not there is an alpha channel. Provide support for JPEG 2000 raw codestreams (`.j2k` files), as well as boxed JPEG 2000 files (`.j2p` or `.jpx` files).

This flag should be enabled if there is a need to handle JPEG 2000 images.

### lcms
Write the `enable_lcms = True` option to the `setup.cfg` build configuration file. Build and install the `PIL.ImageCms` Python module to provide color profile management support using the LittleCMS2 color management engine, based on Kevin Cazabon’s PyCMS library.

This flag should be enabled if there is a need to work with color profiles.

### test
Execute the `selftest.py --installed` and `pytest -p no:relaxed` commands inside of the virtual Xvfb session after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend a build time.

This flag should normally be disabled as it is mainly useful for developers, tester and maintainers.

### tiff
Write the `enable_tiff = True` option to the `setup.cfg` build configuration file. Use the `libtiff` library to allow PIL to read and write compressed TIFF files. If disabled, PIL will always write uncompressed files.

This flag should be enabled if there is a need to manage compressed TIFF images.

### tk
Make sure that the `tk` flag is enabled for the [dev-lang/python](../dev-lang/python.md) package. Build and install the `PIL.ImageTk` Python module - an ImageTk module that contains support to create and modify Tkinter BitmapImage and PhotoImage objects from PIL images.

This flag should be enabled if there is a need to produce native images for the Tk GUI toolkit.

### truetype
Write the `enable_freetype = True` option to the `setup.cfg` build configuration file. Build and install the `PIL.ImageFont` Python module that uses the FreeType library and provides a class to store bitmap fonts that are used with the `PIL.ImageDraw.Draw.text()` method. Enable support for TrueType and OpenType fonts (as well as other font formats supported by the FreeType library).

This flag should be enabled if there is a need to draw text.

### webp
Write the `enable_webp = True` and `enable_webpmux = True` options to the `setup.cfg` build configuration file. Use the `libwebp` library to provide support to read and write images in the WebP format and an ability to create animated WebP files from non-animated WebP images, extract frames from animated WebP images.

This flag should be enabled if there is a need to work with WebP images.

### xcb
Write the `enable_xcb = True` option to the `setup.cfg` build configuration file.Use the XCB library to provide an ability to capture screenshots using the `ImageGrab.grab()` method.

It is safe to disable this flag.

### zlib
Write the `enable_zlib = True` option to the `setup.cfg` build configuration file. Use the `libz` library to provides support to read and write compressed PNG (Portable Network Graphics) files.

This flag should be enabled if there is a need to work with compressed PNG files.
