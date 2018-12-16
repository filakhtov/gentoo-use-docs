# media-plugins/gst-plugins-vaapi

### drm
Ensure that the `drm` flag is enabled for the [x11-libs/libva](../x11-libs/libva.md) package. Pass the `--enable-drm` option to the configure script. Provide an ability to use the `libva` DRM rendering capabilities.

See the `drm` flag of the [x11-libs/libva](../x11-libs/libva.md) package for more information, including when to enable this flag.

### egl
Pass the `--enable-egl` option to the configure script. Provide an ability to use the EGL API for OpenGL video output, that does nothing on its own, but can be used in combination with OpenGL or GLES for video frames rendering. See the `opengl` and `gles2` flags for details.

This flag should be enabled as a dependency of the `opengl` or `gles2` flag and should be disabled otherwise.

### gles2
Requires the `egl` flag to be enabled. Append the `gles2` and `gles3` values to the `--with-glapi` option that is passed to the configure script. Provide an ability to use the OpenGL ES (OpenGL for Embedded Systems, aka GLES) version 2 or 3 to perform hardware-accelerated (usually using GPU) video frames rendering.

This flag should be enabled on embedded systems that have OpenGL ES version 2 or 3.

### opengl
Requires the `egl` or `X` flag to be enabled. Append the `gl` value to the `--with-glapi` option and pass it to the configure script. When enabled together with the `X` option, also pass the `--enable-glx` option to the configure script to provide an ability to output video using the GLX (OpenGL Extension for X Window System). Otherwise, the EGL API will be used instead for rendering video using the OpenGL API.

This flag should be enabled if the target system supports OpenGL hardware acceleration.

### wayland
Pass the `--enable-wayland` option to the configure script. Make sure that

See the `wayland` flag of the [x11-libs/libva](../x11-libs/libva.md) package for more information, including when to enable this flag.

### X
Pass the `--enable-x11` option to the configure script. Provide an ability to use `libva` X window system rendering capabilities for video output. See the `opengl` flag for possibly better alternative.

See the `X` flag of the [x11-libs/libva](../x11-libs/libva.md) package for more information, including when to enable this flag.
