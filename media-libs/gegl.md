# media-libs/gegl

### cairo
Pass the `-Dcairo=enabled` and `-Dpangocairo=enabled` options to the meson build script. Use the Cairo and Pango libraries to enable additional image processing operations, such as displaying a string of text, render a brush stroke, perform a n-point image deformation, render a vector stroke, draw a filled region, render a Spyrograph pattern or render luminance profile for RGB components.

This flag can be safely disabled if the aforementioned operations aren't needed.

### debug
This flag does nothing after the switch to use Meson build system.

### ffmpeg
Pass the `-Dlibav=enabled` option to the meson build script. Use the FFmpeg library to provide an ability to load video frames and write them back into the video output sink.

This flag can be safely disabled, if there is no need to perform video frame manipulation via the GEGL library.

### introspection
Pass the `-Dintrospection=true` option to the meson build script. Generate and install the `Gegl-0.4.gir` GIR metadata file that provides bindings for the GEGL libraries to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### lcms
Pass the `-Dlcms=enabled` option to the meson build script. Use the LCMS v2 library to convert the input image from an ICC color (International Color Consortium) profile to a well defined babl format for further processing.

This flag should be enabled if there is a need to handle color profiles.

### lensfun
Pass the `-Dlensfun=enabled` option to the configure script. Enable the lens distortion correction support.

It is safe to disable the flag.

### openexr
Pass the `-Dopenexr=enabled` option to the meson build script. Use the OpenEXR library to provide an ability to read from and write to an EXR image format.

It is safe to disable the flag.

### pdf
Pull in the [app-text/poppler](../app-text/poppler.md) package as a dependency and ensure that the `cairo` flag is enabled for it. Use Poppler bindings via the Glib interface to allow reading pages from PDF files.

This flag can be safely disabled.

### raw
Pass the `-Dlibraw=enabled` option to the meson build script. Use the `libraw` library to provide an ability to read RAW camera image files.

It is safe to disable the flag.

### sdl
Pass the `-Dsdl=enabled` option to the meson build script. Enable support for the `sdl-display` to allow displaying the input buffer in an SDL window.

This flag can be safely disabled.

### svg
Requires a `cairo` flag to be enabled. Pass the `-Dlibrsvg=enabled` option to the meson build script. Use the `librsvg` library to provide an ability to load SVG image files.

It is safe to disable the flag.

### test
Exclude some known broken tests. Pass the `-Dpygobject=enabled` option to the meson build script. Execute the `meson test` command to run the test suite provided with the source code and check for regressions after the main build is completed. This will extend overall build time.

This flag should normally be disabled, because this kind of tests is oriented towards developers, maintainers and testers.

### tiff
Pass the `-Dlibtiff=enabled` option to the meson build script. Use the `libtiff` library to provide an ability to load and save TIFF (DescriptionTagged Image File Format) images.

It is safe to disable the flag.

### umfpack
Pass the `-Dumfpack=enabled` option to the meson build script. Create a foreground alpha map given a sparse supplied tri-map and an input image, then set white as selected and black as unselected.

The flag can be safely disabled.

### v4l
Pass the `-Dlibv4l=enabled` and `-Dlibv4l2=enabled` options to the meson build script. Enable integration with both the `libv4l` and `libv4l2` libraries to provide an ability to get a frame from Video4Linux input devices, such as webcams.

It is safe to disable the flag.

### vala
Requires an `introspection` flag to be enabled. Pass the `-Dvapigen=enabled` option to the meson build script. Generate and install the `gegl-0.4.vapi` Vala bindings file that provides an access to the Gegl library using the GObject Introspection framework.

The flag can be safely disabled if there is no need to use GEGL in Vala programs.

### webp
Pass the `-Dwebp=enabled` option to the meson build script script. Link against the `libwebp` library to provide an ability to read and write WebP images.

It is safe to disable the flag.
