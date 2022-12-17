# x11-libs/cairo

### aqua
Pass the `-Dquartz=enabled` option to the Meson build script. Enable support for rendering cairo graphics onto Quartz surfaces, targeting the Apple macOS Quartz rendering system.

This flag should be disabled as it is only useful on the macOS.

### debug
Pass the `-Dsymbol-lookup=enabled` option to the Meson build script. Provide an ability to look up backtrace information using the symbol table and the dwarf line information using the `libbfd` library in order to convert addresses to line number and function name for debugging purposes.

This flag should normally be disabled.

### gles2-only
This flag only works if the `opengl` flag is disabled. Pass the `-Dgl-backend=glesv2` option to the Meson build script. Provide an ability for Cairo to perform on screen draw operations with hardware acceleration using the OpenGL ES 2.0 API via the EGL interface.

This flag should normally be disabled, unless for embedded systems with the OpenGL ES 2.0 support and no full fledged OpenGL support.

### gles3
Only works if the `gles2-only` flag is enabled and does the same, but pass the `-Dgl-backend=glesv3` option to the Meson build script to use the OpenGL ES 3.0 API instead.

This flag should normally be disabled, unless on embedded systems without full fledged OpenGL support, but with the OpenGL ES 3.0 support.

### glib
Pass the `-Dglib=enabled` option to the Meson build script. Build and install the `libcairo-gobject` library that contains helper functions to integrate Cairo with a Glib's GObject system. These functions are used for GObject introspection to provide dynamic bindings for the Cairo library.

The flag can be safely disabled.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the Meson build script. Use the Gtk-Doc tool to generate the API reference manual in the HTML format and install it into the `/usr/share/gtk-doc` directory.

It is safe to disable this flag.

### opengl
Pass the `-Dgl-backend=gl` option to the Meson build script. Build Cairo with the cairo-gl backend that provides an implementation of possibly hardware-accelerated rendering by targeting the OpenGL API. It aims to provide better performance with equal functionality to cairo-image where possible. Supports GLX, WGL and EGL.

This flag can be safely disabled.

### test
Pass the `-Dtests=enabled` option to the Meson build script. Build the test suite provided with the source code and execute the `meson test` command after the main build is completed to run it and check for any regressions. This will extend the build time.

This flag should normally be disabled, because it is primarily oriented towards the developers, maintainers and testers.

### X
Pass the `-Dtee=enabled`, `-Dxlib=enabled` and `-Dxcb=enabled` options to the Meson build script.

- Enable the XLib surface to render cairo graphics to X Window System windows and pixmaps using the XLib and Xrender libraries.
- Provide support for the tee surface backend that multiplexes all operations performed on it to the one or more underlying surfaces, mainly used by Mozilla applications.
- Enable the XCB surface that can be used to render cairo graphics to X Window System windows and pixmaps using the XCB library.

It is safe to disable this flag.
