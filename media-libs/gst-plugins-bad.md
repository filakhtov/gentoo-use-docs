# media-libs/gst-plugins-bad

### bzip2
This option is broken after [media-libs/gst-plugins-bad](../media-libs/gst-plugins-bad.md) switched to the Meson build system. It should bass the `-Dbz2=enabled` option to the Meson build script, but doesn't. This is a bug in the Gentoo ebuild.

Do not enable this flag.

### egl
Ensure that the `egl` flag is enabled on the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package.

See the base package description for details.

### gles2
Ensure that the `gles2` flag is enabled on the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package. Pass the `-Dgl=enabled` option to the Meson build script. Enable GStreamer OpenGL API integration support which is used by various plugins.

See the base package description for details.

### gtk
This flag is used for transition between build systems only and should not be enabled yet.

### introspection
Pass the `-Dintrospection=enabled` option to the Meson build script. Generate and install the `GstPlayer-1.0.gir`, `GstMpegts-1.0.gir`, `GstWebRTC-1.0.gir` and `GstInsertBin-1.0.gir` GIR metadata files to provide dynamic bindings for the `libgstplayer`, `libgstmpegts`, `libgstwebrtc` and `libgstinsertbin` libraries respectively to languages other than C, using the GObject Introspection framework.

It is safe to disable the flag.

### nls
Pass the `-Dnls=enabled` option to the configure script. Use the Gettext library to provide an ability to translate programs messages into different languages based on the system locale settings.

This flag can be safely disabled, unless there is a need to use a non-English language.

### opengl
Ensure that the `opengl` flag is enabled on the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package. Pass the `-Dgl=enabled` option to the Meson build script. Enable GStreamer OpenGL API integration support which is used by various plugins.

See the base package description for details.

### orc
Pass the `-Dorc=enabled` option to the Meson build script. Use the `liborc` library that provides the ORC (Oil Runtime Compiler, OIL stands for Optimized Inner Loops) runtime compiler that is used to perform hardware-accelerated multimedia processing, utilizing CPU-specific SIMD instructions, like MMX or 3DNOW. When disabled, unoptimized (and thus slow) backup C code will be used instead.

It is recommended to enable this flag if the target system supports ORC to improve performance.

### test
Pass the `-Dtests=enabled` option to the Meson build script. Build the test suite provided with the source code and execute the `ninja test` command inside of the virtual Xvfb session to run it after the main build is completed. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.

### vnc
Only works if the `X` flag is enabled. Pass the `-Dlibrfb=enabled` option to the Meson build script. Build and install the `libgstrfbsrc` library from the `gst-plugins-bad` upstream package that allows to connect to a VNC server and decode an RFB (Remote FrameBuffer) stream to display or record the contents of the screen.

This flag should only be enabled if there is a need to access VNC servers through GStreamer framework.

### wayland
Pass the `-Dwayland=enabled` option to the Meson build script. Build and install the `libgstwaylandsink` library from the `gst-plugins-bad` upstream package that provides the `waylandsink` that is able to render video output into the Wayland surface. It is creating its own Wayland window and renders the decoded video frames to that.

This flag should only be enabled on systems that run Wayland as a display manager.

### X
This flag is only used if the `vnc` flag is enabled. It is using the `libX11` library as an optional, but "automagic" dependency (i.e. will be automatically used if available in the system at the build time) to allow to send key press events to a machine running VNC server, i.e. control that machine over the VNC protocol.

It is safe to disable the flag.
