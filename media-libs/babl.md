# media-libs/babl

### introspection
Pass the `-Denable-gir=true` option to the Meson build script. Generate and install the `Babl-0.1.gir` GIR metadata file and the accompanying typelib to provide dynamic bindings for the `libbabl` library to languages other than C using the GObject introspection framework.

It is safe to disable the flag.

### lcms
Pass the `-Dwith-lcms=true` option to the Meson build script. Link against the lcms2 library to provide support for CMYK (Cyan, Magenta, Yellow, Black) color profiles.

This flag can be safely disabled.
