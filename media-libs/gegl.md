# media-libs/gegl

### cairo
Pass the `--with-cairo` and `--with-pangocairo` options to the configure script. Use the Cairo and Pango libraries to enable additional image processing operations, such as displaying a string of text, render a brush stroke, perform a n-point image deformation, render a vector stroke, draw a filled region, render a Spyrograph pattern or render luminance profile for RGB components.

This flag can be safely disabled if the aforementioned operations aren't needed.

### debug
Pass the `--enable-debug` option to the configure script. Enable debugging symbols in the produced libraries and produce additional debugging output, such as reporting leaked buffer allocations, displaying information about processing and rendering operations, etc.

It is recommended to disable the flag, unless there is a need to enable debugging code.

### ffmpeg
Pass the `--with-libavformat` option to the configure script (also pass the `--with-gexiv2` option if a `test` flag is enabled). Use the FFmpeg library to provide an ability to load video frames and write them back into the video output sink.

This flag can be safely disabled, if there is no need to perform video frame manipulation via the GEGL library.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `Gegl-0.4.gir` GIR metadata file that provides bindings for the GEGL libraries to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### lcms
Pass the `--with-lcms` option to the configure script. Use the LCMS library to convert the input image from an ICC color (International Color Consortium) profile to a well defined babl format for further processing.

This flag should be enabled if there is a need to handle color profiles.

### lensfun
Pass the `--with-lensfun` option to the configure script. Enable the lens distortion correction support.

It is safe to disable the flag.

### libav
Only works when a `ffmpeg` flag is enabled. When enabled, use the Libav library instead of the FFmpeg to read and write video frames.

This flag should only ever be toggled system-wide, because Libav and FFmpeg can't be installed on the same system at the same time.

### openexr
Pass the `--with-openexr` option to the configure script. Use the OpenEXR library to provide an ability to read from and write to an EXR image format.

It is safe to disable the flag.

### pdf
Pass the `--with-popplerglib` option to the configure script. Use Poppler bindings via the Glib interface to allow reading pages from PDF files.

This flag can be safely disabled.

### raw
Pass the `--with-libraw` option to the configure script. Use the `libraw` library to provide an ability to read RAW camera image files.

It is safe to disable the flag.

### sdl
Pass the `--with-sdl` option to the configure script. Enable support for the `sdl-display` to allow displaying the input buffer in an SDL window.

This flag can be safely disabled.

### svg
Requires a `cairo` flag to be enabled. Pass the `--with-librsvg` option to the configure script. Use the `librsvg` library to provide an ability to load SVG image files.

It is safe to disable the flag.

### test
Execute the `make check` command to run the test suite provided with the source code and check for regressions after the main build is completed. This will extend overall build time.

This flag should normally be disabled, because this kind of tests is oriented towards developers, maintainers and testers.

### tiff
Pass the `--with-libtiff` option to the configure script. Use the `libtiff` library to provide an ability to load and save TIFF (DescriptionTagged Image File Format) images.

It is safe to disable the flag.

### umfpack
Pass the `--with-umfpack` option to the configure script. Create a foreground alpha map given a sparse supplied tri-map and an input image, then set white as selected and black as unselected.

The flag can be safely disabled.

### v4l
Pass the `--with-libv4l` and `--with-libv4l2` options to the configure script. Enable integration with both the `libv4l` and `libv4l2` libraries to provide an ability to get a frame from Video4Linux input devices, such as webcams.

It is safe to disable the flag.

### vala
Requires an `introspection` flag to be enabled. Pass the `--with-vala` option to the configure script. Generate and install the `gegl-0.4.vapi` Vala bindings file that provides an access to the Gegl library using the GObject Introspection framework.

The flag can be safely disabled if there is no need to use GEGL in Vala programs.

### webp
Pass the `--with-webp` option to the configure script. Link against the `libwebp` library to provide an ability to read and write WebP images.

It is safe to disable the flag.

### zlib
Pass the `--with-zlib` option to the configure script. Use the `libz` library to enable buffer compression using the DEFLATE algorithm.

This flag can be safely disabled.
