# media-libs/harfbuzz

### cairo
Pass the `-Dcairo=enabled` option to the meson build script. Build and install the `hb-view` tool to generate a graphical view of a string shape, using a particular font, as a set of glyphs.

It is safe to disable the flag.

### debug
By default, sanity checks that are intended for debugging and are safe and recommended to disable in production are built. When this flag is disabled, append `-DHB_NDEBUG` option to the `CPPFLAGS` variable for a duration of the build and therefore disable simple memory allocation and deallocation checks and related assertions.

This flag should only be enabled if there is a need to debug the library itself or any linked applications.

### doc
Pass the `-Ddocs=enabled` option to the meson build script. Use the Gtk-Doc tool to generate documentation in the HTML format and install it into the `/usr/share/gtk-doc/harfbuzz` directory. The documentation includes a user manual with library description, installation, usage steps, concepts description, library API developer reference and so forth.

This flag can be safely disabled.

### glib
Pass the `-Dglib=enabled` option to the meson build script. Use the `GLib` library for Unicode support, provide GObject introspection, build the `hb-view`, `hb-shape`, `hb-ot-shape-closure` and `hb-subset` tools and the `libharfbuzz-subset` and `libharfbuzz-gobject` libraries.

It is recommended to enable this flag as many packages (e.g. the Pango library) depend on provided features.

### graphite
Pass the `-Dgraphite=enabled` option to the meson build script script. Provide support for Graphite fonts - TrueType fonts with additional tables containing smart rendering information via the `libgraphite2` library.

This flag should be enabled if there is a need to use Graphite fonts, e.g. for non-roman script languages.

### icu
Pass the `-Dicu=enabled` option to the meson build script. Build and install the `libharfbuzz-icu` library that provides a drop-in replacement for the ICU Layout Engine designed to handle logical order of glyphs in complex scripts.

It is safe to disable the flag.

### introspection
Pass the `-Dgobject=enabled` and the `-Dintrospection=enabled` options to the meson build script. Generate the `HarfBuzz-0.0.gir` GIR metadata file during build time and compile a typelib from it to provide dynamic HarfBuzz library bindings to languages other than C.

This flag can be safely disabled.

### static-libs
Pass the `-Dstatic=true` option to the meson build script. Build and install a statically linked version of the `libharfbuzz` library (also the `libharfbuzz-gobject` and the `libharfbuzz-subset` libraries if the `glib` flag is enabled and the `libharfbuzz-icu` library if the `icu` flag is enabled).

The flag should only ever be enabled if there is a need for the static libraries.

### test
Pass the `-Dtests=enabled` option to the meson build script. Prepare a Python environment to properly run the tests and execute the test suite provided with the source code during the build to check for any regressions. This will extend a build time.

It is recommended to disable the flag as it is mainly useful for the Gentoo team, testers and developers.

### truetype
Pass the `-Dfreetype=enabled` option to the configure script. Use the `freetype` library for loading fonts and glyph metrics instead of using `HarfBuzz`'s internal font functions.

This flag should be enabled to improve font shaping.
