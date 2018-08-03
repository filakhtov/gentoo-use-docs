# media-libs/mesa

### bindist
Pass the `--disable-texture-float` option to the configure script. When disabled, enable support for OpenGL floating point textures and render targets and install the `patents.txt` document that contains information about the patented code that can't be redistributed in the binary format into the `/usr/share/doc/mesa-<VERSION>` directory.

**NOTE:** Pattent has expired on 18th of June 2018 so this flag does not have aforementioned implication, but it has not been updated in the Portage tree yet.

This flag should be enabled to support floating-point textures in OpenGL applications.

### classic
Append the `swrast` value to the `--with-dri-drivers=` option passed to the configure script. Execute the `make install` command from the `src/mesa/drivers/dri` source tree subdirectory to install DRI libraries. Build and install the `swrast_dri.so` library - the legacy/original Mesa software rasterizer and drivers that are selected via the `VIDEO_CARDS` variable. Move all libraries into the `/usr/lib/dri/mesa` subdirectory from the `/usr/lib/dri` directory and create symlinks back, then remove symlinks to the `swrast_dri.so` library and supported driver libraries enabled via the `VIDEO_CARDS` variable so that they can be managed by the `eselect` tool. Execute the `eselect mesa set --auto` command when build is completed to set defaults.

This flag should only be enabled as a dependency of one or more video card drivers or if there is an explicit need for the `swrast` rasterizer.

### d3d9
Pass the `--enable-nine` option to the configure script. Build the `libd3dadapter9.so` library that provides support for the Nine Direct3D9 API. Nine implements the full IDirect3DDevice9 COM interface and a custom COM interface called ID3DAdapter9 which is used to implement a final IDirect3D9Ex COM interface.

This flag should be enabled to run applications that use Direct3D9 API, e.g. via Wine.

### debug
If the `llvm` flag is enabled, ensure that [sys-devel/llvm](../sys-devel/llvm.md) is built with the `debug` flag too. Pass the `--enable-debug` option to the configure script. Use debug compiler flags (pass `-g` option) and macros (pass `-DDEBUG` option) and disable optimizations (pass `-O0` option). Compile libraries and binaries with debugging symbols. Enable additional runtime assertions and print extra debugging messages during execution.

This flag should only be enabled if there is a need to debug the Mesa libraries/drivers or applications linked against them.

### dri3
Pass the `--enable-dri3` option to the configure script. Enable support for the DRI3 (Direct Rendering Infrastructure 3) extension that utilizes the DMA-BUF (Direct Memory Access Buffer Sharing API) feature to pass buffer objects between X Server and DRI client using file descriptors over the old and insecure GEM (Graphics Execution Manager) buffer sharing mechanism.

This flag should be enabled if target systems runs the X Server.

### egl
Pass the `--with-platforms=x11,surfaceless` and the `--enable-egl` options to the configure script. Build and install the `libEGL` library that provides the EGL API entry points and helper functions for use by the drivers. EGL API handles graphics context management, surface/buffer binding, and rendering synchronization and enables high-performance, accelerated, mixed-mode 2D and 3D rendering for the Embedded-System Graphics. This feature is formerly known as Eagle.

This flag should be enabled on embedded systems that support Khronos rendering APIs, such as OpenGL ES or OpenVG.

### gallium
Pass the `--with-gallium-drivers=swrast` option to the configure script. Enable Gallium3D - a new architecture for building 3D graphics drivers that is designed to allow portability to all major operating systems and graphics interfaces. Build and install `swrast_dri.so` library and other supported driver libraries enabled via the `VIDEO_CARDS` variable into the `/usr/lib/dri` directory. Rename all these drivers and libraries and append a `g` suffix to their original names (to indicate Gallium versions), e.g. `swrast_dri.so` becomes `swrastg_dri.so`. Execute the `eselect mesa set --auto` command when build is completed to set defaults.

This flag should only be enabled as a dependency of one or more video card drivers and other Mesa features or if there is an explicit need for the `Gallium3D` backend, e.g. for software rendering without hardware acceleration.

### gbm
Pass the `--enable-gbm` option to the configure script, also append a `drm` value to the `--with-platforms` option if the `egl` flag is enabled. Build and install a `libgbm.so` library that provides a graphics buffer manager (aka GBM) - an abstraction of the graphics driver specific buffer management APIs (for instance the various `libdrm_*` libraries), implemented internally by calling into the Mesa GPU drivers.

This flag should only be enabled as a dependency of the graphics driver or if the target system runs the Wayland display server.

### gles1
Pass the `--enable-gles1` option to the configure script. Build and install the `libGLESv1_CM` library that provides support for the OpenGL ES 1.1 API - a royalty-free, cross-platform API for rendering advanced 2D and 3D graphics on embedded and mobile systems - including consoles, phones, appliances and vehicles. OpenGL ES depends on a working EGL implementation.

This flag should be enabled on the embedded systems that support OpenGL ES 1.1 API.

### gles2
Pass the `--enable-gles2` option to the configure script. Build and install the `libGLESv2` library that provides support for the OpenGL ES 2.0 API - a royalty-free, cross-platform API for rendering advanced 2D and 3D graphics on embedded and mobile systems - including consoles, phones, appliances and vehicles. OpenGL ES depends on a working EGL implementation.

This flag should be enabled on the embedded systems that support OpenGL ES 2.0 API.

### llvm
This flag only works if the `gallium` flag is enabled. Prepare build environment by detecting a latest installed version of the LLVM package and appending it to the `PATH` variable. Pass the `--enable-llvm` option to the configure script. Build and install the Gallium llvmpipe driver - a software rasterizer that uses LLVM to do runtime code generation. Shaders, point/line/triangle rasterization and vertex processing are implemented with LLVM IR which is translated to x86, x86-64, or ppc64le machine code. Also, the driver is multithreaded to take advantage of multiple CPU cores (up to 8 at this time). It's the fastest software rasterizer for Mesa.

This flag should only be enabled as a dependency of a Gallium3D driver or when software rendering without hardware acceleration is necessary.

### nptl
Pass the `--enable-glx-tls` option to the configure script. Enable the ELF (Executable Linux Format) TLS (Thread Local Storage) support. The `LibGL` will store the dispatch table pointer in TLS area to avoid the expensive call to `pthread_getspecific` and the test of `_glapi_Dispatch`.

This flag should be enabled on any platform capable of using TLS.

### opencl
This feature only works with a Gallium3D driver. Pass the `--enable-opencl` and the `--with-clang-libdir=/usr/lib` options to the configure script. Build and install the `libOpenCL.so` library into the `/usr/lib/OpenCL/vendors/mesa` directory and the `opencl.h` include file into the `/usr/lib/OpenCL/vendors/mesa/include` directory to allow dynamic switching via the `eselect` tool. Provide support for the OpenCL 1.1 API - the open, royalty-free standard for cross-platform, parallel programming of diverse processors found in personal computers, servers, mobile devices and embedded platforms. Mesa mainly supports OpenCL on AMD cards. Execute the `eselect opencl set --use-old mesa` option after the main build is completed to switch to Mesa OpenCL implementation if there is no other provider.

This flag should only be enabled if there is a need to use the OpenCL API.

### openmax
This feature only works with a Gallium3D driver. Pass the `---enable-omx-bellagio` option to the configure script. Use the OpenMAX Bellagio library to provide support for the OpenMAX (Open Media Acceleration) API - a royalty-free cross-platform set of interfaces that provide abstractions for routines useful for efficient processing of audio, video, and still images intended for low power and embedded system devices.

This flag should be enable on embedded platforms where OpenMAX support is available and necessary.

### osmesa
Pass the `--enable-osmesa` (or the `--enable-gallium-osmesa` if the `gallium` flag is enabled) option to the configure script. Build and install the `libOSMesa` library - an off-screen interface for rendering into user-allocated memory without any sort of window system or operating system dependencies, meaning the GL_FRONT colorbuffer is actually a buffer in main memory, rather than a window on your display.

It is safe to disable this flag.

### pax_kernel
Pass the `--enable-glx-read-only-text` option to the configure script. Disable writable `.text` section on `x86` platform necessary for running mesa under the PaX hardened Kernel. For details see [Gentoo Bug #240956](https://bugs.gentoo.org/240956).

This flag must only be enabled on hardened systems.

### pic
Pass the `--disable-asm` option to the configure script. Disable Assembly code that is used for performance optimization on `x86` platform in order to build PIC (position independent code) libraries (however, `-fPIC` compiler flag must be set in order to do so).

This flag should be enabled on hardened systems or if there is an explicit need for the PIC libraries.

### selinux
This flag is unused, it should be disabled.

### unwind
Pass the `--enable-libunwind` option to the configure script. This flag only makes sense if the `debug` flag is enabled too. Use the `libunwind` library to generate backtraces for debugging messages.

This flag should normally be disabled and is only useful for debugging purposes.

### vaapi
This feature only works with a Gallium3D driver. Pass the `--enable-va` and the `--with-va-libdir=/usr/lib/va/drivers` options to the configure script. Enable support for the VA API (Video-Acceleration API) via the `libva` library to gain an access to graphics hardware acceleration capabilities for video processing. Support accelerated encoding and decoding of the MPEG2, VC-1, H.264/AVC, etc. formats.

It is recommended to enable this flag if there is a need to deal with encoding and decoding video files using a compatible GPU, e.g. AMD.

### valgrind
Pass the `--enable-valgrind=auto` option to the configure script. Build mesa with Valgrind support. Enable some sanitization and additional code to supress false positive reports from Valgrind in various memory management routines and Kernel calls. This has a performance impact.

This flag should only be enabled if there is a need to run Valgrind tool on the application linked against mesa libraries.

### vdpau
This feature only works for Gallium3D drivers. Pass the `--enable-vdpau` option to the configure script. Enable support for VDPAU (Video Decode and Presentation API) via the `libvdpau` library to access video decoding acceleration and presentation hardware present in modern GPUs. Support accelerated encoding and decoding of the MPEG-1, MPEG-2, MPEG-4 part 2, H.264, VC-1 and DivX formats.

It is recommended to enable this flag if there is a need to deal with video files encoding and decoding using a compatible GPU, e.g. Nvidia with Nouveau driver.

### vulkan
Pass the `--with-vulkan-drivers` option with a list of supported drivers enabled via `VIDEO_CARDS` to the configure script. Build and install drivers that utilize Vulkan API - a new generation graphics and compute API that provides high-efficiency, cross-platform access to modern GPUs used in a wide variety of devices. Currently only modern AMD and Intel GPUs are supported.

It is highly recommended to enable this flag if the target system has the AMD or Intel GPU.

### wayland
The Wayland server requires the EGL implementation and GBM support to work. Append the `wayland` value to the `--with-platforms` option and pass it to the configure script. Provide an implementation of the EGL API for Wayland clients to draw directly to the framebuffer.

This flag should only be enabled if there is a need to run Wayland server on the target system.

### xa
This feature only works for Gallium3D drivers. Pass the `--enable-xa` option to the configure script. Build and install the XA (X.Org Acceleration) state tracker developed by VMWare. It provides versioning support, surface functionality, and YUV blits for textured X-Video, Solid fills without ROP functionality, Copies with format conversion and reinterpretation but without ROP, Xrender-type compositing for general acceleration. It is primarily designed for use by the `vmwgfx` on VMware-virtualized guest operating systems. The Freedreno driver uses XA for accelerating 2D with open-source, reverse-engineered Qualcomm graphics driver.

This flag should only be enabled if the target system runs inside of VMWare machine or runs on Adreno GPU with Freedreno driver.

### xvmc
The feature only works with a Gallium3D driver. Pass the `--enable-xvmc` option to the configure script. Enable the XvMC (X-Video Motion Compensation) API support - an X.Org Server extension that allows video programs to offload portions of the video decoding process to the GPU video-hardware. It is old and outdated extension that is currently obsolete by VA-API and VDPAU and is disabled by default in Mesa.

This flag should normally be disabled and VA-API or VDPAU should be used instead. However it can be used for old hardware that has no such capabilities.
