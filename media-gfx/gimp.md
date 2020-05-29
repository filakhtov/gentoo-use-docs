# gimp

### aalib
Pass the `--with-aa` option to the configure script. Use the `aalib` library to provide an ability to generate an ASCII art graphic from an actual image.

It is safe to disable the flag.

### alsa
Pass the `--with-alsa` option to the configure script. Use the ALSA (Advanced Linux Sound Architecture) library to provide an ability to control GIMP using MIDI devices.

This flag should normally be disabled.

### aqua
Pass the `--with-x` option to the configure script when this flag is disabled. When enabled, GIMP will use macOS native Aqua user interface and [x11-libs/gtk-mac-integration](../x11-libs/gtk-mac-integration.md) integration toolkit instead of traditional X.Org.

This option should be disabled as it is only useful for macOS systems.

### debug
Pass the `--enable-debug=yes` option to the configure script. Pass additional debugging flags to the compiler and produce libraries and binaries with debugging symbols.

This flag should normally be disabled.

### doc
Pass the `--enable-gtk-doc` option to the configure script. Use the GTK-Doc to build the API documentation for libraries provided by GIMP from the source code, instead of installing prebuilt version provided in the release archive.

This flag should normally be disabled.

### gnome
Pull in the [gnome-base/gvfs](../gnome-base/gvfs.md) package as a dependency. Enable the "Open Location" functionality that can be used to load images from a network location, provided a URL, e.g. from an FTP (File Transfer Protocol) server, web page over HTTP (Hyper Text Transfer Protocol), windows shares over the SMB (Server Message Block) protocol and so on.

It is safe to disable the flag.

### heif
Pass the `--with-libheif` option to the configure script. Use the `libheif` library to provide an ability to load and save images in the HEIF (High Efficiency Image Format, aka HEIC - High Efficiency Image Codec) format. Modern Apple devices use HEIC instead of JPEG when taking photos.

This flag can be safely disabled.

### jpeg2k
Pass the `--with-jpeg2000` option to the configure script. Use the OpenJPEG library to enable support for loading the JPEG-2000 image format. GIMP can't create JPEG-2000 files.

It is safe to disable the flag.

### mng
Pass the `--with-libmng` option to the configure script. Use the `libmng` library to provide an ability to export images in the MNG (Multiple-Image Network Graphics) format. GIMP can not load images stored in the MNG format.

This flag can be safely disabled.

### openexr
Pass the `--with-openexr` option to the configure script. Use the OpenEXR library to provide an ability to load and export images in the EXR format, the professional-grade image storage format of the motion picture industry.

It is safe to disable the flag.

### postscript
Pass the `--with-gs` option to the configure script. Use the Ghostscript interpreter for the PostScript language to read and write PS (PostScript) and EPS (Extended PostScript) files.

This flag can be safely disabled.

### python
Prepare the build environment to find suitable Python interpreter version. Pass the `--enable-python` option to the configure script. Generate and install GIMP-Python set of modules that act as a wrapper to the `libgimp` library and can be used to create GIMP plugins using the Python interpreter with the full set of Python extension modules.

This flag should normally be disabled.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run the test suite provided with the source code to check for regressions. This will extend a build time.

This flag should normally be disabled. It is primarily intended for maintainers, testers and developers.

### udev
Pass the `--with-gudev` option to the configure script. Use the GObject bindings for the `libudev` to enable support for various input devices, such as tablets.

It is safe to disable the flag.

### unwind
Pass the `--with-libunwind` option to the configure script. Use the `libunwind` library to produce reliable stack traces (especially in the multithreaded scenarios) that are used for profiling or crash reporting.

This flag can be safely disabled.

### vector-icons
Pass the `--enable-vector-icons` option to the configure script. Use scalable vector icons (rather than raster) for user interface elements.

It is recommended to enable this flag.

### webp
Pass the `--with-webp` option to the configure script. Use the `libwebp` library to enable support for loading and saving images in WebP format, including animations, ICC profiles as well as EXIF (EXchangeable Image File) and XMP (eXtensible Metadata Platform) metadata.

This flag can be safely disabled.

### wmf
Pass the `--with-wmf` option to the configure script. Use the `libwmf` library to allow loading vector images in Microsoft's native WMF (Windows Metafile Format) format.

This flag should normally be disabled.

### xpm
Pass the `--with-libxpm` option to the configure script. Use the `libxpm` library to provide an ability to load and save images in the XPM format (X Pixelmap Color Bitmap for X Window System).

It is safe to disable the flag.
