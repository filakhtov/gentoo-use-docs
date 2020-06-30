# media-libs/gst-plugins-bad

### bzip2
Pass the `--enable-bz2` option to the configure script. Build and install the `libgstbz2` library from the `gst-plugin-bad` upstream package to provide an ability to compress or decompress streams using the Bzip2 format.

This flag should be enabled to support Bzip2 compression, e.g. when handling compressed streams in Matroska files.

### introspection
Make sure that the `introspection` flag is enabled for both the [media-libs/gstreamer](../media-libs/gstreamer.md) and the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) packages. Pass the `--enable-introspection` option to the configure script. Generate and install the `GstPlayer-1.0.gir`, `GstMpegts-1.0.gir`, `GstWebRTC-1.0.gir` and `GstInsertBin-1.0.gir` GIR metadata files to provide dynamic bindings for the `libgstplayer`, `libgstmpegts`, `libgstwebrtc` and `libgstinsertbin` libraries respectively to languages other than C, using the GObject Introspection framework.

It is safe to disable the flag.

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to provide an ability to translate programs messages into different languages based on the system locale settings.

This flag can be safely disabled, unless there is a need to use a non-English language.

### orc
Pass the `--enable-orc` option to the configure script. Use the `liborc` library that provides the ORC (Oil Runtime Compiler, OIL stands for Optimized Inner Loops) runtime compiler that is used to perform hardware-accelerated multimedia processing, utilizing CPU-specific SIMD instructions, like MMX or 3DNOW. When disabled, unoptimized (and thus slow) backup C code will be used instead.

It is recommended to enable this flag if the target system supports ORC to improve performance.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run the test suite provided with the source code to check for regressions. This will extend the build time.

This flag should normally be disabled as it is primarily oriented towards maintainers, testers and developers.

### vnc
Only works if the `X` flag is enabled. Pass the `--enable-librfb` option to the configure script. Build and install the `libgstrfbsrc` library from the `gst-plugins-bad` upstream package that allows to connect to a VNC server and decode an RFB (Remote FrameBuffer) stream to display or record the contents of the screen.

This flag should only be enabled if there is a need to access VNC servers through GStreamer framework.

### wayland
Pass the `--enable-wayland` option to the configure script. Build and install the `libgstwaylandsink` library from the `gst-plugins-bad` upstream package that provides the `waylandsink` that is able to render video output into the Wayland surface. It is creating its own Wayland window and renders the decoded video frames to that.

This flag should only be enabled on systems that run Wayland as a display manager.

### X
This flag is only used if the `vnc` flag is enabled. It is using the `libX11` library as an optional, but "automagic" dependency (i.e. will be automatically used if available in the system at the build time) to allow to send key press events to a machine running VNC server, i.e. control that machine over the VNC protocol.

It is safe to disable the flag.
