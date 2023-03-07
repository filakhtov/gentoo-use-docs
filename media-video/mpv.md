# media-video/mpv

### alsa
Pass the `-Dalsa=enabled` option to the Meson build script. Enable support for the ALSA audio input and output to provide an ability to access sound hardware via the ALSA (Advanced Linux Sound Architecture) subsystem. This allows `mpv` to play sound through ALSA devices and is used for audio capture from V4L2 devices (see the `v4l` flag for details).

This flag should be enabled if the target system uses ALSA as the main audio output system.

### aqua
Pass the `-Dcocoa=enabled` option, as well as `-Dgl-cocoa=enabled` and `-Dvideotoolbox-gl=enabled` options if the `opengl` flag is also enabled, to the Meson build script. Use the native Cocoa API for rendering decoded video frames on an Apple macOS system.

This flag should normally be disabled as it is intended for a macOS system.

### archive
Pass the `-Dlibarchive=enabled` option to the Meson build script. Use the `libarchive` library to provide an ability to demultiplex compressed media streams. A list of supported compression algorithms depends on build options of the `libarchive` library itself.

It is safe to disable the flag, unless there is a need to play compressed multiplexed media streams.

### bluray
Pass the `-Dlibbluray=enabled` option to the Meson build script. Use the `libbluray` library to provide an ability to play Blu-ray discs and their images. Blu-ray media can be accessed through the `bd://` protocol.

This flag should only be enabled if there is a need to read Blu-ray discs or images.

### cdda
Pass the `-Dcdda=enabled` option to the Meson build script. Use the `libcdio` library to provide an ability to play the CDDA (Compact Disc Digital Audio, aka Audio CD) discs.

This flag should only be enabled if there is a need to play Audio CDs.

### cli
Pass the `-Dcplayer=enabled`, `-Dhtml-build=enabled` and `-Dmanpage-build=enabled` options to the Meson build script. Build and install the `mpv` comman-line player, associated manpages and HTML documentation. This is what most of users would want and is not necessary if an alternative front-end will be used. If enabled together with the `luajit` flag, then disable the PaX MPROTECT restrictions from the resulting binary to prevent issues with Just-in-Time code generation.

This flag should normally be enabled if the mpv to be used as a standalone player, and can be safely disabled if only the `libmpv` is needed.

### coreaudio
Pass the `-Dcoreaudio=enabled` option to the Meson build script. Build and install the `coreaudio` output driver - native macOS audio driver that uses AudioUnits and CoreAudio sound server to play sound.

This flag should be disabled as it is only relevant for Apple macOS systems.

### debug
Add the `-DNDEBUG` option to the `CFLAGS`, `CXXFLAGS`, `...FLAGS` variables for the duration of the build. Produce libraries and binaries with debugging information attached.

This flag should normally be disabled, unless there is a need to perform debugging.

### drm
Pass the `-Ddrm=enabled` and `-Dgbm=enabled` options to the Meson build script. Enable the `drm` video output driver that is using Kernel Mode Setting subpart of the Direct Rendering Manager to output decoded video frames and provide an ability to store decoded video frames in a GBM (Graphics Buffer Manager) buffer for subsequent rendering via the EGL API.

This flag should be enabled if there is a need to play videos without full-blown graphical environment, i.e. X or Wayland server.

### dvb
Pass the `-Ddvbin=enabled` option to the Meson build script. Provide an ability to watch DVB (Digital Video Broadcasting) television through mpv. Enable support for the set of runtime `--dvbin` options and the `dvb://` protocol.

This flag should only be enabled if there is a need to watch DVB streams.

### dvd
Pass the `-Ddvdnav=enabled` option to the Meson build script. Provide an ability to play DVD video discs and disc images using either the `libdvdnav` and `libdvdread`. Normally, mpv prefers the `libdvdnav` when playing DVDs using the `dvd://` protocol handle and can be explicitly accessed using the `dvdnav://` handle, while the `libdvdread` can be accessed using the `dvdread://` one.

This flag should be enabled if there is a need to play DVD media or images.

### egl
Requires the `X`, `drm` or `wayland` flag to be enabled. Provide an ability to render decoded video frames using the EGL API on top of different backends.

When enabled together with the `X` flag, then also pass the `-Degl-x11=enabled` option to the Meson build script to allow to use the X Window System implementation of the EGL API. It can be useful on an embedded system that has only OpenGL ES capabilities and runs an X server. See the `X` flag for additional details.

If enabled together with the `drm` flag, pass the `-Degl-drm=enabled` option to the Meson build script to provide an ability to use the DRM (Direct Rendering Manager) implementation for the EGL API via the Mesa GBM. This allows to use the OpenGL output without a full-featured window system. See the `drm` flag for more details.

For hardware-accelerated video decoding with EGL rendering, see the `vaapi` flag.

See the `wayland` flag for details on EGL use with Wayland.

This flag should be enabled if there is a need for one of the EGL based video outputs.

### gamepad
Pass the `-Dsdl2-gamepad=enabled` and `-Dsdl2=enabled` option to the Meson build script. Use the SDL2 library to provide an ability to control the player using gamepads. Controls can be associated with various actions, such as seek, play, pause, etc, via configuration file.

This flag should only be enabled if there is a need to use an SDL2 gamepad with mpv.

### iconv
Pass the `-Diconv=enabled` option to the Meson build script. Use the `libiconv` library to perform subtitles text conversion into UTF-8 encoding.

This flag should be enabled if there is a need to use subtitles encoded using a non-UTF-8 character set.

### jack
Pass the `-Djack=enabled` option to the Meson build script. Build and install the `jack` output audio driver that can be used to play sound through the JACK (Jack Audio Connection Kit) system.

This flag should normally be disabled, unless JACK is used as a main audio output on the target system.

### javascript
Pass the `-Djavascript=enabled` option to the Meson build script. Provide support for JavaScript plugins using the MuJS - a compatible minimal ES5 (ECMAScript version 5) interpreter. JavaScript API provided is similar to what of the Lua with some minor differences.

This flag should only be enabled if there is a need to write or use JavaScript plugins.

### jpeg
Pass the `-Djpeg=enabled` option to the Meson build script. Use the `libjpeg` library to provide an ability to save screenshots in the JPEG (Joint Photographic Experts Group) image format.

It is safe to disable this flag, unless there is a need to take JPEG screenshots.

### lcms
Pass the `-Dlcms2=enabled` option to the Meson build script. Use the Little CMS color management system (version 2) to provide an ability to apply ICC (International Color Consortium) color profiles to decoded video frames before rendering them.

This flag should be enabled if there is a need to apply color profile when watching videos.

### libcaca
Pass the `-Dcaca=enabled` option to the Meson build script. Build and install the `caca` video output driver, that uses the `libcaca` library to render video frames as a color ASCII art and can display them on a text console.

This flag should normally be disabled.

### libmpv
Pass the `-Dlibmpv=true`, `-Dgl=enabled` and `-Dplain-gl=enabled` options to the Meson build script. Build and install the shared `libmpv` library that can be used by other programs as a video and audio playback backend, including the OpenGL rendering capabilities, without platform-specific implementation (in which case a library client will have to provide one).

This flag should be enabled if mpv is not to be used directly, but with some frontend interface, such as gnome-mpv.

### libplacebo
Pass the `-Dlibplacebo=enabled` option to the Meson build script. Enable support for GPU accelerated video rendering using the `libplacebo` library.

It is recommended to enabled this flag to enable hardware accelerated video rendering.

### lua
Pass the `-Dlua=enabled` option to the Meson build script. Allow to load and execute external Lua scripts to extend mpv functionality, i.e. control mpv in a similar way to slave mode using the client API via the provided `mp` Lua module. Install additional Lua scripts into the `/usr/share/mpv` directory, including the `acompressor.lua` that adds keyboard shortcuts to control the dynamic range compression FFmpeg filter, `ao-null-reload.lua` that handles the edge case where attempts to init audio output fails, `autocrop.lua` that uses the lavfi cropdetect filter to automatically apply the crop filter with appropriate paramteres for the currently playing video, and others.

This flag should be enabled if there is a need to use Lua scripting to control the player.

### mmal
Pass the `-Drpi-mmal=enabled` option to the Meson build script. Enable support for Raspberry Pi MMAL (Multimedia Abstraction Layer) hardware acceleration.

This flag should only ever be enabled on compatible platforms witm MMAL support.

### nvenc
Pass the `-Dcuda-hwaccel=enabled` and `-Dcuda-interop=enabled` options to the Meson build script. Enable support for hardware accelerate video decoding using compatible NVIDIA cards.

It is safe to disable this flag, and should only be enabled on systems that use a supported NVIDIA gpu.

### openal
Pass the `-Dopenal=enabled` option to the Meson build script. Build and install the `openal` audio output driver that can utilize the OpenAL API to play sound, usually multichannel three-dimensional positional audio.

This flag should normally be disabled, unless there is a need to play 3D audio.

### opengl
Requires either one of the `aqua` or `X` flags to be enabled. Pass the `-Dgl=enabled` option to the Meson build script. Provide an ability to use the OpenGL API to render decoded video frames into the specified output. See the `aqua` and `X` flags for more information on how the OpenGL API is used in different scenarios.

It is recommended to enable this flag together with an appropriate video output flag to perform accelerated video rendering.

### pipewire
Pass the `-Dpipewire=enabled` option to the Meson build script. Build the `pipewire` audio driver that can be used to play audio through PipeWire audio server.

This flag should be enabled if the target system uses the PipeWire server as a main sound system.

### pulseaudio
Pass the `-Dpulse=enabled` option to the Meson build script. Build the `pulse` audio driver, that can be used to play audio through a PulseAudio server.

This flag should be enabled if the target system uses the PulseAudio server as a main sound system.

### raspberry-pi
Pass the `-Drpi=enabled` option to the Meson build script. Provide an ability to perform hardware-accelerated video decoding on Raspberry-PI platform.

This flag should only be enabled on Raspberry-PI hardware.

### rubberband
Pass the `-Drubberband=enabled` option to the Meson build script. Build and install the `rubberband` filter that uses the Rubber Band audio time-stretching and pitch shifting library to allow to dynamically change tempo and pitch of an audio stream.

This flag should normally be disabled, unless there is an explicit need to apply this filter.

### sdl
Pass the `-Dsdl2=enabled`, `Dsdl2-audio=enabled` and `-Dsdl2-video=enabled` options to the Meson build script. Provide an ability to render video frames and audio output using the SDL2 (Simple DirectMedia Layer, version 2) library, that works on systems with and without hardware acceleration.

This flag should only be enabled on systems that don't provide proper graphics drivers, or which support OpenGL ES only.

### selinux
Pull in the [sec-policy/selinux-mplayer](../sec-policy/selinux-mplayer.md) package as a dependency, that provides a set of SELinux policy definitions, required for proper operation of the mpv player under a SELinux-restricted kernel.

This flag should only ever be toggled system-wide, i.e. as a part of a SELinux-enabled Portage profile.

### sixel
Pass the `-Dsixel=enabled` option to the Meson build script. Use the `libsixel` to enable `sixel` video backend that can render output using DEC's Sixel (short for "six pixels") bitmap format.

This flag should normally be disabled.

### sndio
Pass the `-Dsndio=enabled` option to the Meson build script. Build and install the `sndio` audio backend that uses the `libsndio` library to play audio through sndio audio and Midi server.

It is safe to disable this flag.

### test
Requires the `cli` flag to be enabled. Pass the `-Dtests=enabled` option to the Meson build script. Build the regression test suite and execute resulting binaries when the main build is completed to check for any regressions. This will extend the build time.

This flag should normally be disabled as it is oriented towards maintainers, testers and developers.

### tools
Requires the `cli` flag to be enabled. Install additional tools:

- `mpv_identify.sh` script, that can be used to get (and print) media file properties, such as media format and length, video fps and bitrate, etc;
- `umpv` Python script (for every active Python target), that emulates "unique application" by reusing already opened mpv window to play media;
- `mpv_idet.sh` script (named `idet.sh` in the source), that uses the FFmpeg's "idet" filter for interlace deteciton;

It is safe to disable the flag.

### uchardet
Pass the `-Duchardet=enabled` option to the Meson build script. Use the `libuchardet` library to provide an ability to automatically detect a character encoding of subtitle files.

The flag can be safely disabled, unless there is a need to deal with non-UTF-8 subtitle files.

### vaapi
Requires at least one of the `egl`, `X`, `libplacebo` or `drm` (if the `wayland` flag is enabled) flag to be enabled. Pass the `-Dvaapi=enabled` option to the Meson build script. Use the VA-API (Video Acceleration API) to perform hardware-accelerated video decoding and postprocessing.

If enabled together with the `X` flag, also pass the `-Dvaapi-x11=enabled` option to the Meson build script to provide an ability to render decoded frames directly from the VA-API pipeline onto the X server drawable area. If the `egl` flag is enabled together with the `X` flag, then pass the `-Dvaapi-x-egl=enabled` flag that can also use the EGL API for rendering utilizing the X Window System as a backend.

When enabled together with the `wayland` flag, also pass the `-Dvaapi-wayland=enabled` option to the Meson build script. Provide an ability to render video frames onto Wayland surface, necessary when running the Wayland display server.

If the `drm` flag is also enabled, additionally pass the `-Dvaapi-drm=enabled` option to the Meson build script. Use the GBM (Generic Buffer Management) API to store decoded frames into the graphics buffer.

It is recommended to enable this flag on systems with supported hardware, e.g. Intel or AMD/Radeon GPUs, to enable hardware-accelerated video decoding and processing.

### vdpau
Requires the `X` flag to be enabled. Pass the `-Dvdpau=enabled` option to the Meson build script. Use the VDPAU (Video Decode and Presentation API for Unix) API to perform hardware accelerated video decoding and postprocessing. When enabled together with the `opengl` flag, additionally pass the `-Dvdpau-gl-x11=enabled` option to the Meson build script to provide an ability to render decoded video frames using the OpenGL API.

This flag should be enabled on systems with supported hardware, i.e. ones with old Nvidia GPUs that don't support CUDA, to perform hardware-accelerated video decoding. For modern Nvidia cards, the `nvenc` flag can be used instead.

### vulkan
Pass the `-Dvulkan=enabled` and `-Dshaderc=enabled` options to the Meson build script. Provide an ability to use the Vulkan graphics API for video presentation using the shaderc library (Google's C wrapper around glslang) to translate mpv's GLSL (aka GLslang - official OpenGL Shading Language) shaders into Vulkan's SPIR-V (Standard Portable Intermediate Representation) format.

This flag should normally be disabled, because this feature is still under very early stages of development, unless these is an explicit need to use the Vulkan API as a video output.

### wayland
Pass the `-Dwayland=enabled` option to the Meson build script. Enable the Wayland SHM (shared memory) video output to render decoded frames. If enabled together with the `egl` flag, also pass the `-Degl-wayland=enabled` option to the Meson build script to provide an ability to use EGL renderer to display video frames within Wayland window system. For hardware accelerated video decoding, see the `vaapi` flag.

This flag should be enabled on systems that use the Wayland display server.

### X
Pass the `-Dx11=enabled` option to the Meson build screen. Enable the x11 video output, that has no hardware acceleration, i.e. is slow and provides an ability to output video frames into a drawable area of the X server.

If enabled together with the `opengl` flag, then pass the `-Dgl-x11=enabled` option to the Meson build script to perform hardware-accelerated video rendering using the GLX (OpenGL extension for X Window System), which is considered legacy and deprecated.

If enabled together with the `egl` flag, then provides an ability to perform hardware-accelerated rendering of frames using the EGL API, see the `egl` flag for more details.

For hardware accelerated video decoding, see the `vaapi` and `vdpau` flags.

This flag should be enabled on the systems that run X Window System and preferably together with at least one of the `opengl`, `egl`, `vaapi`, `vdpau` or `xv` flags.

### xv
Requires the `X` flag to be enabled. Pass the `-Dxv=enabled` option to the Meson build script. Provide an ability to output video frames using the X Video extension (aka XVideo or Xv) for the X Window System.

This flag should be enabled for systems that use the X Window system, but can not use the `opengl`, `egl`, `vaapi` and `vdpau` flags, e.g. due to hardware limitations.

### zimg
Pass the `-Dzimg=enabled` option to the Meson build script. Use the `libzimg` library to enable support for high-quality software based image scaling.

This flag should only be enable if a target platform has no hardware accelerate image scaling capabilities.

### zlib
Pass the `-Dzlib=enabled` option to the Meson build script. Use the `libz` library to provide an ability to decompress zlib-compressed streams from Matroska media container (mkv files).

It is recommended to enable this flag if there is a need to play Matroska files.
