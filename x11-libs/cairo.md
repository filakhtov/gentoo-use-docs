# x11-libs/cairo

### aqua
Pass the `--enable-quartz` and the `--enable-quartz-image` options to the configure script. Enable support for rendering cairo graphics onto Quartz surfaces, targeting the Apple macOS Quartz rendering system.

This flag should be disabled as it is only useful on the macOS.

### debug
Pass the `--enable-test-surfaces` option to the configure script. Enable support for "test" surface backends suitable for testing and debugging that can be used as a good starting point for creating custom backends.

It is safe to disable this flag.

### gles2
Pass the `--enable-glesv2` option to the configure script. Provide an ability for Cairo to draw something on screen with hardware acceleration using the OpenGL ES 2.0 API via the EGL interface.

It is recommended to enable this flag on embedded systems with the OpenGL ES 2.0 support.

### glib
Pass the `--enable-gobject` option to the configure script. Build and install the `libcairo-gobject` library that contains helper functions to integrate Cairo with a Glib's GObject system. These functions are used for GObject introspection to provide dynamic bindings for the Cairo library.

The flag can be safely disabled.

### opengl
Pass the `--enable-gl` option to the configure script. Build Cairo with the cairo-gl backend that provides an implementation of possibly hardware-accelerated rendering by targeting the OpenGL API. It aims to provide better performance with equal functionality to cairo-image where possible. Supports GLX, WGL and EGL.

It is safe to disable this flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libcairo`, the `libcairo-script-interpreter` and other Cairo libraries.

This flag should only be enabled if there is a need for the static libraries.

### svg
Pass the `--enable-svg` option to the configure script. Build Cairo library with the SVG surface support that is used to render Cairo graphics to SVG files and is a multi-page vector surface backend.

It is safe to disable the flag.

### valgrind
Pass the `--enable-valgrind` option to the configure script. Enable and build additional code that is necessary to properly handle false positive reports of memory leaks while running an application linked against Cairo library under the Valgrind debugging tool.

This flag should normally be disabled.

### X
Pass the `--with-x`, `--enable-xlib`, `--enable-xlib-xrender` and the `--enable-tee` options to the configure script. When disabled, patch the `Makefile.am` file to exclude the `boilerplate`, `test` and `perf` directories from being build.

- Enable the XLib surface to render cairo graphics to X Window System windows and pixmaps using the XLib and Xrender libraries.
- Provide support for the tee surface backend that multiplexes all operations performed on it to the one or more underlying surfaces, mainly used by Mozilla applications.

It is safe to disable this flag.

### xcb
Pass the `--enable-xcb` and the `--enable-xcb-shm` options to the configure script. Enable support for the XCB surface to allow rendering cairo graphics to X Window System windows and pixmaps using the XCB library. Also supports XCB SHM (Shared Memory Extension) API.

This flag can be safely disabled.