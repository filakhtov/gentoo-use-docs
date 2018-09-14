# media-libs/gst-plugins-base

### alsa
Pass the `--enable-alsa` option to the configure script. Build and install the `libgstalsa` plugin library that provides an ability to fetch ALSA MIDI sequencer events and makes them available to elements understanding audio/x-midi-events in their sink pads and can be used to generate notes from a MIDI input device, and also to output to and read from a sound card via ALSA.

This flag should be enabled if there is a need to use GStreamer framework with the ALSA subsystem.

### egl
Only works if the `opengl` or the `gles2` flag is enabled. Ensure that [media-libs/mesa](../media-libs/mesa.md) package has `egl` flag enabled. Pass the `--enable-egl` option to the configure script. Enable support for Khronos EGL API to provide an access to an underlying native platform window system. This is an alternative to the GLX (X Server OpenGL interface) extension.

This flag should be enabled for systems that need to use OpenGL API outside of an X Server, for example with Wayland.

### gbm
Only makes sense if the `opengl` or the `gles2` flag is enabled. The GBM (Generic Buffer Management) is an "automagic" dependency, so this flag ensures that the [media-libs/mesa](../media-libs/mesa.md) package has `gbm` flag enabled and pull in the [dev-libs/libgudev](../dev-libs/libgudev.md) and the [x11-libs/libdrm](../x11-libs/libdrm.md) packages as dependencies. Provide an ability for devices that have GPUs with libdrm support to use Mesa3D's GBM (Generic Buffer Manager) library to set up an EGL context directly on top of KMS and makes it possible to use the GStreamer OpenGL elements without a windowing system.

This flag should be enabled if there is a need to use GBM backend, for example, when using GStreamer with Wayland.

### gles2
Ensure that [media-libs/mesa](../media-libs/mesa.md) package has `gles2` flag enabled. Pass the `--enable-gles2` option to the configure script. Provide same features that the `opengl` flag provides, but use OpenGL ES (OpenGL for Embedded Systems) API, a subset available for supported embedded systems, instead of the full-featured OpenGL implementation.

This flag should be enabled to provide OpenGL features on supported embedded systems.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the following GIR metadata files: `GstAudio-1.0.gir` to provide dynamic bindings for the `libgstaudio` library, `GstRtp-1.0.gir` for `libgstrtp-1.0.gir`, `GstSdp-1.0.gir` for `libgstsdp-1.0.gir`, `GstRtsp-1.0.gir` for `libgstrtsp`, `GstVideo-1.0.gir` for `libgstvideo`, `GstApp-1.0.gir` for `libgstapp`, `GstAllocators-1.0.gir` for `libgstallocators`, `GstPbutils-1.0.gir` for `libgstpbutils`, `GstRiff-1.0.gir` for `libgstriff`, `GstTag-1.0.gir` for `libgsttag`, and fi the `opengl` or `gles2` flag is enable also `GstGL-1.0.gir` for the `libgstgl` library, to languaguages other than C using the GObject Introspection infrastructure.

It is safe to disable the flag.

### ivorbis
Pass the `--enable-ivorbis` option to the configure script. Build and install the `libgstivorbisdec` plugin library that uses the Tremor library to decode raw vorbis streams to integer audio.

This flag should be enabled on platforms that have no support for floating point operations.

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to translate programs and plugins messages at runtime into various languages based on system locale settings.

This flag should be enabled if there is a need to use GStreamer framework in a non-English language.

### ogg
Pass the `--enable-ogg` option to the configure script. Use the `libogg` library to provide support for handling media stored in the OGG container, including parsing, muxing and demuxing audio, video and text streams.

This flag should be enabled if there is a need to work with OGG media.

### opengl
Pass the `--enable-opengl` option to the configure script. Build and install `libgstopengl` and `libgstgl` libraries. Provide the `glimagesink` sink to render video frames to a drawable on a local or remote display using the OpenGL API. Depends on the driver, hardware accelerated scaling of video frames and color conversion using OpenGL shaders, conversion of stereoscopic/multiview video formats, GL Shading Language effects and OpenGL scenes rendering might be supported.

This flag should be enabled to provide full-featured OpenGL support.

### orc
Pass the `--enable-orc` option to the configure script. Use the `liborc` library (Optimized Inner Loops Runtime Compiler) for SIMD and other optimizations to improve performance. Without Orc slow unoptimised backup code will be used for many performance critical code paths.

It is generally recommended to enable this flag to improve performance.

### pango
Pass the `--enable-pango` option to the configure script. Build and install the `libgstpango` plugin library that provides an ability to render and overlay text atop of the video stream, e.g. current clock time, subtitles, text stamps of the extracted frame, etc.

This flag should be enabled if there is a need to handle text rendering.

### theora
Pass the `--enable-theora` option to the configure script. Build and install the `libgsttheora` plugin that uses the `libtheora` library to parse raw theora streams, decode them into raw YUV video and encode raw YUV back to theora stream.

This flag should be enabled if there is a need to handle theora video streams.

### vorbis
Pass the `--enable-vorbis` option to the configure script. Build and install the `libgstvorbis` plugin that uses the `libvorbis` library to parse raw vorbis streams, decode them to float audio, encode audio in the Vorbis format and manipulate vorbis tags.

This flag should be enabled if there is a need to handle the Vorbis format.

### X
Pass the `--enable-x`, `--enable-xshm` and `--enable-xvideo` options to the configure script, also pass the `--enable-glx` option if the `opengl` flag is enabled and the `--enable-x11` option if the `opengl` or the `gles2` flag is enabled. Build and install the `ximagesink` plugin to provide X11 video output element based on standard Xlib calls, `xvimagesink` plugin that renders video frames to a drawable (XWindow) on a local display using the XVideo extension and provide an ability to send data over shared memory to the matching source using the `shmsink` sink. Also enable support for the GLX (X Server OpenGL API) extension for OpenGL rendering.

This flag should be enabled to output video to drawable X server areas.

### wayland
Only works if the `opengl` or the `gles2` flag is enabled. Pass the `--enable-wayland` option to the configure script. Integrate with Wayland windowing system, provide the `waylandsink` that is used for creating its own window and render the decoded video frames to that. Current implementation uses EGL and is based on Weston compositor.

This flag should be enabled if the target system runs Wayland display server.
