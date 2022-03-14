# media-video/mpv

### alsa
Pass the `--enable-alsa` option to the waf build script. Build and install the ALSA audio drivers that provide an ability to access sound hardware to play sound through devices, that can be accessed via the ALSA (Advanced Linux Sound Architecture) subsystem. It is also used for audio capture from V4L2 devices (see the `v4l` flag for details).

This flag should be enabled if the target system uses ALSA as the main audio output system.

### aqua
Requires the `opengl` flag to be enabled. Pass the `--enable-cocoa` and `--enable-gl-cocoa` options to the waf build script. Use the native Cocoa API for rendering decoded video frames on an Apple macOS system.

This flag should normally be disabled as it is only working on a macOS system.

### archive
Pass the `--enable-libarchive` option to the waf build script. Use the `libarchive` library to provide an ability to demultiplex compressed media streams. A list of supported compression algorithms depends on build options of the `libarchive` library itself.

It is safe to disable the flag, unless there is a need to play compressed multiplexed media streams.

### bluray
Pass the `--enable-libbluray` option to the waf build script. Use the `libbluray` library to provide an ability to play Blu-ray discs and their images. Blu-ray media can be accessed through the `bd://` protocol.

This flag should only be enabled if there is a need to read Blu-ray discs or images.

### cdda
Pass the `--enable-cdda` option to the waf build script. Use the `libcdio` library to provide an ability to play the CDDA (Compact Disc Digital Audio, aka Audio CD) discs.

This flag should only be enabled if there is a need to play Audio CDs.

### cli
Build and install the `mpv` binary, that is a command-line interface of the player. This is what most of users would want and is not necessary if an alternative front-end will be used. If enabled together with the `luajit` flag, then disable the PaX MPROTECT restrictions from the resulting binary to prevent issues with Just-in-Time code generation. When disabled, pass the `--disable-cplayer` option to the waf build script to disable the command-line interface.

This flag should normally be enabled if the mpv to be used as a standalone player, and can be safely disabled if only the `libmpv` is necessary.

### coreaudio
Pass the `--enable-coreaudio` option to the waf build script. Build and install the `coreaudio` output driver - native macOS audio driver that uses AudioUnits and CoreAudio sound server to play sound.

This flag should be disabled as it is only relevant for Apple macOS.

### cplugins
Pass the `--enable-cplugins` option to the waf build script. Enable support for mpv plugins written in C. These scripts can be automatically loaded from the scripts directory specified by the config or explicitly given via the `--script` runtime option.

This flag should be enabled if there is a need to write or use plugins written in C language.

### cuda
This flag can be used together with the `libav` flag and requires the `opengl` one to be enabled. Pass the `--enable-cuda-hwaccel` option to the waf build script. Enable hardware accelerated video decoding using the Nvidia CUDA video decoder (aka CUVID or NVDEC), including the MPEG-2, VC-1 and H.264 formats, and supported formats depend on the available hardware.

This flag should be enabled on systems with supported hardware, i.e. where any modern Nvidia GPU is a primary graphics card or the only one.

### debug
Pass the `--enable-debug-build` to the waf build script. Pass the `-g` option to the compiler invocation to produce libraries and binaries with debugging information attached.

This flag should normally be disabled, unless there is a need to perform debugging.

### doc
Pass the `--enable-pdf-build` option to the waf build script. Use the `rst2pdf` tool to generate a PDF version of the documentation out of the rst (reStructuredText) markup files and install it into the `/usr/share/doc/mpv-<VERSION>` directory.

It is safe to disable the flag.

### drm
Pass the `--enable-drm` option to the configure script. Enable the `drm` video output driver that is using Kernel Mode Setting subpart of the Direct Rendering Manager to output decoded video frames.

This flag should be enabled if there is a need to play videos without full-blown graphical environment, i.e. X or Wayland server.

### dvb
Pass the `--enable-dvbin` option to the waf build script. Provide an ability to watch DVB (Digital Video Broadcasting) television through mpv. Enable support for the set of runtime `--dvbin` options and the `dvb://` protocol.

This flag should only be enabled if there is a need to watch DVB streams.

### dvd
Pass the `--enable-dvdnav` and `--enable-dvdread` option to the waf build script. Provide an ability to play DVD video discs and disc images using either the `libdvdnav` or `libdvdread`. Normally, mpv prefers the `libdvdnav` when playing DVDs using the `dvd://` protocol handle and can be explicitly accessed using the `dvdnav://` handle, while the `libdvdread` can be accessed using the `dvdread://` one.

This flag should be enabled if there is a need to play DVD media or images.

### egl
Requires the `X`, `gbm` or `wayland` flag to be enabled. Provide an ability to render decoded video frames using the EGL API on top of different backends.

When enabled together with the `X` flag, then also pass the `--enable-egl-x11` option to the waf build script to allow to use the X Window System implementation of the EGL API. It can be useful on an embedded system that has only OpenGL ES capabilities and runs an X server. See the `X` flag for additional details.

If enabled together with the `gbm` flag, pass the `--enable-egl-drm` option to the waf build script to provide an ability to use the DRM (Direct Rendering Manager) implementation for the EGL API via the Mesa GBM. This allows to use the OpenGL output without a full-featured window system. See the `gbm` flag for more details.

For hardware-accelerated video decoding with EGL rendering, see the `vaapi` flag.

This flag should be enabled if there is a need for one of the EGL based video outputs.

### gamepad
Pass the `--enable-sdl2-gamepad` option to the waf build script. Use the SDL2 library to provide an ability to control the player using gamepads. Controls can be associated with various actions, such as seek, play, pause, etc, via configuration file.

This flag should only be enabled if there is a need to use SDL2 gamepad with mpv.

### gbm
Requires the `drm`, `egl` and `opengl` flags to be enabled. Pass the `--enable-gbm` option to the waf build script. Provide an ability to store decoded video frames in q GBM (Graphics Buffer Manager) buffer for subsequent rendering via the EGL API. See the `egl` flag for additional information. See the `vaapi` flag for hardware accelerated video decoding support.

This flag should only be enabled if there is a need to use EGL rendering on top of DRM, without a window server.

### iconv
Pass the `--enable-iconv` option to the waf build script. Use the `libiconv` library to perform subtitles text conversion into UTF-8 encoding.

This flag should be enabled if there is a need to use subtitles encoded using a non-UTF-8 character set.

### jack
Pass the `--enable-jack` option to the waf build script. Build and install the `jack` output audio driver that can be used to play sound through the JACK (Jack Audio Connection Kit) system.

This flag should normally be disabled, unless JACK is used as a main audio output on the target system.

### javascript
Pass the `--enable-javascript` option to the waf build script. Provide support for JavaScript plugins using the MuJS - a compatible minimal ES5 (ECMAScript version 5) interpreter. JavaScript API provided is similar to what of the Lua with some minor differences.

This flag should only be enabled if there is a need to write or use JavaScript plugins.

### jpeg
Pass the `--enable-jpeg` option to the waf build script. Use the `libjpeg` library to provide an ability to save screenshots in the JPEG (Joint Photographic Experts Group) image format.

It is safe to disable this flag, unless there is a need to take JPEG screenshots.

### lcms
Requires the `opengl` flag to be enabled. Pass the `--enable-lcms2` option to the waf build script. Use the Little CMS color management system (version 2) to provide an ability to apply ICC (International Color Consortium) color profiles to decoded video frames before rendering them using the OpenGL API. Color profiling only works with the `opengl` output.

This flag should be enabled if there is a need to apply color profile when watching videos.

### libcaca
Pass the `--enable-caca` option to the waf build script. Build and install the `caca` video output driver, that uses the `libcaca` library to render video frames as a color ASCII art and can display them on a text console.

This flag should normally be disabled.

### libmpv
Pass the `--enable-libmpv-shared` option to the waf build script. Build and install the shared `libmpv` library that can be used by other programs as a video and audio playback backend. When enabled together with the `opengl` flag then also pass the `--enable-plain-gl` option to the waf build script to enable the OpenGL rendering capabilities, without platform-specific implementation (in which case a library client will have to provide one).

This flag should be enabled if mpv is not to be used directly, but with some frontend interface, such as gnome-mpv.

### lua
Pass the `--enable-lua` option to the waf build script. Allow to load and execute external Lua scripts to extend mpv functionality, i.e. control mpv in a similar way to slave mode using the client API via the provided `mp` Lua module. Install additional Lua scripts into the `/usr/share/mpv` directory, including the `acompressor.lua` that adds keyboard shortcuts to control the dynamic range compression FFmpeg filter, `ao-null-reload.lua` that handles the edge case where attempts to init audio output fails, `autocrop.lua` that uses the lavfi cropdetect filter to automatically apply the crop filter with appropriate paramteres for the currently playing video, and others.

This flag should be enabled if there is a need to use Lua scripting to control the player.

### nvenc
Pass the `--enable-cuda-hwaccel` and `--enable-cuda-interop` options to the waf build script. Enable support for hardware accelerate video decoding using compatible NVIDIA cards.

It is safe to disable this flag, and should only be enabled on systems that use a supported NVIDIA gpu.

### openal
Pass the `--enable-openal` option to the waf build script. Build and install the `openal` audio output driver that can utilize the OpenAL API to play sound, usually multichannel three-dimensional positional audio.

This flag should normally be disabled, unless there is a need to play 3D audio.

### opengl
Requires either one of the `aqua`, `egl`, `X`, `raspberry-pi` flags to be enabled or the `cli` flag to be disabled. Provide an ability to use the OpenGL API to render decoded video frames into the specified output. See the `aqua`, `X`, `wayland`, `vaapi` and `vdpau` flags for more information on how the OpenGL API is used in different scenarios. When disabled, pass the `--disable-gl` option to the waf build script to disable OpenGL rendering.

It is recommended to enable this flag together with an appropriate video output flag to perform accelerated video rendering.

### pulseaudio
Pass the `--enable-pulse` option to the waf build script. Build the `pulse` audio driver, that can be used to play audio through a PulseAudio server.

This flag should be enabled if the target system uses the PulseAudio server as a main sound system.

### raspberry-pi
Requires the `opengl` flag to be enabled. Modify the `CFLAGS` and `LDFLAGS` variables to make compiler aware of the Raspberry-PI specific include files and libraries. Pass the `--enable-rpi` option to the waf build script. Provide an ability to perform hardware-accelerated video decoding on Raspberry-PI platform.

This flag should only be enabled on Raspberry-PI hardware.

### rubberband
Pass the `--enable-rubberband` option to the waf build script. Build and install the `rubberband` filter that uses the Rubber Band audio time-stretching and pitch shifting library to allow to dynamically change tempo and pitch of an audio stream.

This flag should normally be disabled, unless there is an explicit need to apply this filter.

### sdl
Pass the `--enable-sdl2` option to the waf build script. Provide an ability to render video frames and audio output using the SDL2 (Simple DirectMedia Layer, version 2) library, that works on systems with and without hardware acceleration.

This flag should only be enabled on systems that don't provide proper graphics drivers, or which support OpenGL ES only.

### selinux
Pull in the [sec-policy/selinux-mplayer](../sec-policy/selinux-mplayer.md) package as a dependency, that provides a set of SELinux policy definitions, required for proper operation of the mpv player under a SELinux-restricted kernel.

This flag should only ever be toggled system-wide, i.e. as a part of a SELinux-enabled Portage profile.

### test
Pass the `--enable-test` option to the waf build script. Build the regression test suite and execute resulting binaries when the main build is completed to check for regressions. This will extend the build time.

This flag should normally be disabled as it is oriented towards maintainers, testers and developers.

### tools
Requires the `cli` flag to be enabled. Install additional tools:

- `mpv_identify.sh` script, that can be used to get (and print) media file properties, such as media format and length, video fps and bitrate, etc;
- `umpv` Python script (for every active Python target), that emulates "unique application" by reusing already opened mpv window to play media;
- `mpv_idet.sh` script (named `idet.sh` in the source), that uses the FFmpeg's "idet" filter for interlace deteciton;

It is safe to disable the flag.

### uchardet
Pass the `--enable-uchardet` option to the waf build script. Use the `libuchardet` library to provide an ability to automatically detect a character encoding of subtitle files.

The flag can be safely disabled, unless there is a need to deal with non-UTF-8 subtitle files.

### vaapi
Requires at least one of the `gbm`, `X` or `wayland` flag to be enabled. Pass the `--enable-vaapi` and `--enable-vaapi-hwaccel` options to the waf build script. Use the VA-API (Video Acceleration API) to perform hardware-accelerated video decoding and postprocessing.

If enabled together with the `X` flag, also pass the `--enable-vaapi-x11` option to the waf build script to provide an ability to render decoded frames directly from the VA-API pipeline onto the X server drawable area. When the `opengl` flag is enabled in addition to the `X` flag, then also pass the `--enable-vaapi-glx` option that allows to use the GLX (OpenGL Extension to the X Window System) for rendering decoded output. If the `egl` flag is enabled together with the `X` flag, then pass the `--enable-vaapi-x-egl` flag that can also use the EGL API for rendering utilizing the X Window System as a backend.

When enabled together with the `wayland` flag, also pass the `--enable-vaapi-wayland` option to the waf build script. Provide an ability to render video frames onto Wayland surface, necessary when running the Wayland display server.

If the `gbm` flag is also enabled, additionally pass the `--enable-vaapi-drm` option to the waf build script. Use the GBM (Generic Buffer Management) API to store decoded frames into the graphics buffer.

It is recommended to enable this flag on systems with supported hardware, e.g. Intel or AMD/Radeon GPUs, to enable hardware-accelerated video decoding and processing.

### vdpau
Requires the `X` flag to be enabled. Pass the `--enable-vdpau` and `--enable-vdpau-hwaccel` option to the waf build script. Use the VDPAU (Video Decode and Presentation API for Unix) API to perform hardware accelerated video decoding and postprocessing. When enabled together with the `opengl` flag, additionally pass the `--enable-vdpau-gl-x11` option to the waf build script to provide an ability to render decoded video frames using the OpenGL API.

This flag should be enabled on systems with supported hardware, i.e. ones with old Nvidia GPUs that don't support CUDA, to perform hardware-accelerated video decoding. For modern Nvidia cards, the `cuda` flag should be used instead.

### vulkan
Pass the `--enable-vulkan` and `--enable-shaderc` options to the configure script. Provide an ability to use the Vulkan graphics API for video presentation using the shaderc library (Google's C wrapper around glslang) to translate mpv's GLSL (aka GLslang - official OpenGL Shading Language) shaders into Vulkan's SPIR-V (Standard Portable Intermediate Representation) format.

This flag should normally be disabled, because this feature is still under very early stages of development, unless these is an explicit need to use the Vulkan API as a video output.

### wayland
Requires the `egl` flag to be enabled. Pass the `--enable-wayland` option to the waf build script. Enable the Wayland SHM (shared memory) video output to render decoded frames. If enabled together with the `opengl` flag, also pass the `--enable-gl-wayland` option to the waf build script to provide an ability to use extended OpenGL renderer to display video frames within Wayland window system. For hardware accelerated video decoding, see the `vaapi` flag.

This flag should be enabled on systems that use the Wayland display server.

### X
Pass the `--enable-x11` option to the waf build screen. Enable the x11 video output, that has no hardware acceleration, i.e. is slow and provides an ability to output video frames into a drawable area of the X server. If enabled together with the `opengl` or `egl` flags, then provides an ability to perform hardware-accelerated rendering of frames using the OpenGL API via the GLX (OpenGL Extension to the X Window System) or EGL API respectively. For hardware accelerated video decoding, see the `vaapi` and `vdpau` flags.

This flag should be enabled on the systems that run X Window System and preferably together with at least one of the `opengl`, `egl`, `vaapi`, `vdpau` or `xv` flags.

### xv
Requires the `X` flag to be enabled. Pass the `--enable-xv` option to the waf build script. Provide an ability to output video frames using the X Video extension (aka XVideo or Xv) for the X Window System.

This flag should be enabled for systems that use the X Window system, but can not use the `opengl`, `egl`, `vaapi` and `vdpau` flags, e.g. due to hardware limitations.

### zlib
Pass the `--enable-zlib` option to the waf build script. Use the `libz` library to provide an ability to decompress zlib-compressed streams from Matroska media container (mkv files).

It is recommended to enable this flag if there is a need to play Matroska files.

### zimg
Pass the `--enable-zimg` option to the waf build script. Use the `libzimg` library to enable support for high-quality software based image scaling.

This flag should only be enable if a target platform has no hardware accelerate image scaling capabilities.
