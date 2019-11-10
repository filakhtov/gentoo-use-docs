# media-libs/libmypaint

### gegl
Pass the `--enable-gegl` option to the configure script. Build and install the `libmypaint-gegl` library that provides a bridge between the `libmypaint` and applications that use GEGL (GEneric Graphics Library) based image manipulation and allows to read from and write to the GEGL buffers.

This flag can be safely disabled if `libmypaint` to be used with non-GEGL based apps, such as GIMP or MyPaint itself.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate the `MyPaint-<version>.gir` GIR metadata file (and `MyPaintGegl-<version>.gir` if the `gegl` flag is enabled) to provide dynamic bindings for the `libmypaint` (and `libmypaint-gegl`) library to languages other than C using the GObject introspection framework.

It is safe to disable the flag, unless there is an explicit need for GObject bindings.

### nls
Pass the `--enable-i18n` option to the configure script. Generate and install PO translation files for all supported languages.

This flag can be safely disabled if there is no need to deal with any non-English languages.

### openmp
Pass the `--enable-openmp` option to the configure script. Use the GMP library to enable multiprocessing, i.e. using multiple threads when processing surface tiles.

It is recommended to enable this flag on any modern multi-core or multi-threaded system.
