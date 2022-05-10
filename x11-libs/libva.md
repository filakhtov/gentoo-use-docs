# x11-libs/libva

### drm
DRM support is enabled by default and this flag does nothing at the moment.

### opengl
OpenGL support is enabled by default and this flag does nothing at the moment.

### wayland
Pass the `-Dwith-wayland=true` option to the Meson build script. Build and install the `libva-wayland` library that provides an ability to render decoded and processed video frames onto a Wayland surface. Note: actual backend driver has to support the Wayland rendering too for this to work.

This flag should only be enabled on systems that use the Wayland display server.

### X
Pass the `-Dwith_x11=true` and `-Dwith_glx=true` options to the meson build script. Build and install the `libva-x11` library that provide an ability to render decoded and processed video frames onto the (local) X server drawable areas and the `libva-glx` library that can render decoded and processed video frames as an OpenGL texture, using the GLX (OpenGL Extension to the X Window System). Note: actual backend driver has to support the X11 and OpenGL rendering too for this to work.

This flag should be enabled if the target system runs X window server.
