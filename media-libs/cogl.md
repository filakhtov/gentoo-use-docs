# media-libs/cogl

### debug
Pass a `--enable-debug` option to a configure script. Disable compiler optimizations and include debugging symbols into produced libraries. Display additional debugging information at runtime.

This flag should only ever be enabled for debugging purposes.

### examples
Install developer example files written in C language of how to use a Cogl library into the `/usr/share/doc/cogl-<VERSION>/examples` directory.

It is safe to disable the flag.

### gles2
Pass a `--enable-gles2`, `--enable-cogl-gles2`, `--enable-xlib-egl-platform` and `--with-default-driver=gles2` (an `opengl` flag overrides default value) options to a configure script. Enable an OpenGLES rendering driver and a `libcogl-gles2` library that provides portable access to the OpenGLES API through a single library that is able to smooth over inconsistencies between the different vendor drivers for OpenGLES in a single place.

This flag should be enabled on the embedded systems that support OpenGL ES 2.0 API.

### gstreamer
Pass a `--enable-cogl-gst` option to a configure script. Build and install a `libcogl-gst` library that provides a GStreamer sink which can manage a CoglPipeline to render a video within a Cogl scene.

This flag should be enabled if there is a need to render video frames in scenes rendered using Cogl.

### introspection
Pass a `--enable-introspection` option to a configure script. Generate and install a `Cogl-1.0.gir` and a `Cogl-2.0.gir` GIR metadata files (and also `CoglPango-1.0.gir` if a `pango` flag is enabled, `CoglGst-2.0.gir` if the `gstreamer` flag is enabled) to provide dynamic bindings for respective Cogl libraries to languages other than C using a GObject Introspection framework.

It is safe to disable the flag.

### kms
Pass a `--enable-kms-egl-platform` option to a configure script. Provide an ability to use EGL (Native Platform Graphics Interface) with the KMS (Kernel Mode Setting) subsystem for rendering.

This flag should be enabled if there is a need to run EGL based applications on top of KMS without an X Server.

### opengl
Pass a `--enable-glx`, `--enable-gl` and `--with-default-driver=gl` (takes preference over the `gles2` flag) options to a configure script. Enable an OpenGL rendering driver and enable support for a GLX window system binding API (Open**GL** Extension to the **X** Window System) for output within a window provided by the X Window System.

This flag should be enabled to use Cogl with X Server.

### pango
Pass a `--enable-cogl-pango` option to a configure script. Build and install a `libcogl-pango` library - a Cogl based Pango renderer that can be used to render text that has been layed out by Pango.

This flag should be enabled if there is a need to render text with Cogl library.

### test
Pass a `--enable-unit-tests` option to a configure script. Build a test suite, start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run a test suite provided with the source code. This will extend a build time. When disabled, patch a `Makefile` file to avoid building a test code.

This flag should normally be disabled as these tests are only useful for testers, developers or the Gentoo team.

### wayland
Pass a `--enable-wayland-egl-platform` and `--enable-wayland-egl-server` options to a configure script.

This flag should be enabled to run Cogl with Wayland.
