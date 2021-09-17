# media-plugins/gst-plugins-gtk

### egl
Ensure that the `egl` flag is enabled for the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package to enable Khronos EGL API support.

See [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) for details.

### gles2
Ensure that the `gles2` flag is enabled for the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package to enable support for OpenGL ES (OpenGL for Embedded Systems) API.

See [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) for details.

### opengl
Ensure that the `opengl` flag is enabled for the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package to enable support for OpenGL API.

See [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) for details.

### test
Pass the `-Dtests=enabled` option to the Meson build script. Build the test suite provided with the source code and execute the `ninja test` command inside of the virtual Xvfb session to run it after the main build is completed. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.

### wayland
Ensure that the `wayland` flag is enabled for the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package to integrate with Wayland windowing system.

See [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) for details.

### X
Ensure that the `X` flag is enabled for the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package to integrate with X server video rendering APIs.

See [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) for details.
