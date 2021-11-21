# x11-libs/libva

### drm
Pass the `--enable-drm` option to the configure script. Build and install the `libva-drm` library that can perform "renderless" (or "headless") encoding, decoding, postprocessing, etc of video frames, i.e. saving processed frames directly into a DRM buffer, without having a drawable surface or a window server. It is possible to render DRM buffer contents into drawable area afterwards. Note: actual backend driver has to support the DRM rendering too for this to work.

This flag can be used for renderless processing, e.g. hardware-accelerated video processing on the server.

### opengl
Requires the `X` flag to be enabled. Pass the `--enable-glx` option to the configure script. Build and install the `libva-glx` library that can render decoded and processed video frames as an OpenGL texture, using the GLX (OpenGL Extension to the X Window System). Note: actual backend driver has to support the OpenGL rendering too for this to work. Also note that GLX support for `libva` is considered obsolete in favour of EGL.

This flag should be enabled on systems running the X server with OpenGL extension support.

### utils
Pull in the [media-video/libva-utils](../media-video/libva-utils.md) package as a dependency, that provides utilities and examples to exercise VA-API, including `vainfo` for querying VA-API support, `vp9enc` - a sample VP9 VA-API accelerated encoding program, `h264encode` - a sample H.264 accelerated encoding program and others.

It is safe to disable the flag.

### wayland
Pass the `--enable-wayland` option to the configure script. Build and install the `libva-wayland` library that provides an ability to render decoded and processed video frames onto a Wayland surface. Note: actual backend driver has to support the Wayland rendering too for this to work.

This flag should only be enabled on systems that use the Wayland display server.

### X
Pass the `--enable-x11` option to the configure script. Build and install the `libva-x11` library that provide an ability to render decoded and processed video frames onto the (local) X server drawable areas. Note: actual backend driver has to support the X11 rendering too for this to work.

This flag should be enabled if the target system runs X window server.
