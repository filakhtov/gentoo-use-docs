# media-libs/mesa

### d3d9
Only works if the `gallium` flag is enabled and one of the `intel`, `r300`, `r600`, `radeonsi`, `nouveau` or `vmware` video cards are enabled. Pass the `-Dgallium-nine=true` option to the meson build command. Build the `libd3dadapter9.so` library that provides Direct3D 9.x state tracker. Nine implements the full IDirect3DDevice9 COM interface and a custom COM interface called ID3DAdapter9 which is used to implement a final IDirect3D9Ex COM interface.

This flag should be enabled to run applications that use Direct3D9 API, e.g. via Wine.

### debug
If the `llvm` flag is enabled, ensure that [sys-devel/llvm](../sys-devel/llvm.md) is built with the `debug` flag too (warning will be issued if it is not). Pass the `--buildtype debug` (`plain` if disabled) and `-Db_ndebug=false` (`true` when disabled) options to the meson command. Enable assertions in the meson scripts. Use debug compiler flags (usually `-g` option), disable optimizations (usually `-O0` option) and define the special debugging macro `-DDEBUG`. Compile libraries and binaries with debugging symbols. Enable additional runtime assertions and print extra debugging messages during execution.

This flag should only be enabled if there is a need to debug the Mesa libraries/drivers or applications linked against them.

### gles1
Pass the `-Dgles1=enabled` option to the meson build command. Build and install the `libGLESv1_CM` library that provides support for the OpenGL ES 1.1 API - a royalty-free, cross-platform API for rendering advanced 2D and 3D graphics on embedded and mobile systems - including consoles, phones, appliances and vehicles. OpenGL ES depends on a working EGL implementation.

This flag should be enabled on the embedded systems that support OpenGL ES 1.1 API.

### gles2
Pass the `-Dgles2=enabled` option to the meson build command. Build and install the `libGLESv2` library that provides support for the OpenGL ES 2.0 API - a royalty-free, cross-platform API for rendering advanced 2D and 3D graphics on embedded and mobile systems - including consoles, phones, appliances and vehicles. OpenGL ES depends on a working EGL implementation.

This flag should be enabled on the embedded systems that support OpenGL ES 2.0 API.

### llvm
Prepare build environment by detecting a latest installed version of the LLVM package and appending it to the `PATH` variable. Pass the `-Dllvm=enabled` option to the meson build command. Build and install the Gallium llvmpipe driver - a software rasterizer that uses LLVM to do runtime code generation. Shaders, point/line/triangle rasterization and vertex processing are implemented with LLVM IR which is translated to x86, x86-64, or ppc64le machine code. Also, the driver is multithreaded to take advantage of multiple CPU cores (up to 8 at this time). It's the fastest software rasterizer for Mesa.

This flag should only be enabled as a dependency of a Gallium3D driver or when software rendering without hardware acceleration is necessary.

### lm-sensors
Passe the `-Dlmsensors=enabled` option to the meson build script. Use the `libsensors` library to provide an ability to display temperature, fan speed and other information from the lm_sensors in the Gallium HUD (head-up display).

It is safe to disable the flag.

### opencl
This feature only works with the `r600` and `radeonsi` Gallium3D drivers and requires the `llvm` flag to be enabled. Pass the `-Dgallium-rusticl=true` and `-Drust_std=2021` options to the meson build command. Build and install the `libOpenCL.so` library into the `/usr/lib/OpenCL/vendors/mesa` directory to provide support for the OpenCL 1.1 API - the open, royalty-free standard for cross-platform, parallel programming of diverse processors found in personal computers, servers, mobile devices and embedded platforms.

This flag should only be enabled if there is a need to use the OpenCL API and the target system has supported AMD card.

### osmesa
Pass the `-Dosmesa=true` option to the meson build command. Build and install the `libOSMesa` library - an off-screen interface for rendering into user-allocated memory without any sort of window system or operating system dependencies, meaning the GL_FRONT colorbuffer is actually a buffer in main memory, rather than a window on a display. If you enabling this flag, consider enabling `llvm` as well, otherwise OSMesa will be slow.

It is safe to disable this flag.

### proprietary-codecs
Pass the `-Dvideo-codecs="h264dec,h264enc,h265dec,h265enc,vc1dec"` option to the Meson build script. Enable support for hardware accelerated video encoding and decoding of H.264, H.265 and decoding of VC1 proprietary codecs through the Mesa library.

This flag can be disabled to turn off proprietary video codecs to avoid patent and licensing issues.

### selinux
Pass the `-Dselinux=true` option to the meson build command. Use the `libselinux` library to check if the SELinux restricts executable code in the heap memory and avoids using it for executable section allocation if it is restricted. This is necessary when running under the SELinux-restricted kernel.

This flag should only ever be toggled system-wide, i.e. as part of the SELinux enabled Portage profile.

### test
Pass the `-Dbuild-tests=true` option to the meson build command. Execute the `meson test` command when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, as it is mainly used by maintainers, testers and developers.

### unwind
Only works if the `gallium` flag is enabled. Pass the `-Dlibunwind=enabled` option to the meson build command. Use the `libunwind` library to generate backtraces for debugging messages.

This flag should normally be disabled and is only useful for debugging purposes.

### vaapi
This feature only works with the `d3d12`, `r600`, `radeonsi` or `nouveau` Gallium3D driver. Pass the `-Dgallium-va=enabled`, `-Dva-libs-path=/usr/lib/va/drivers` and, if `d3d12` video driver is enabled, the `-Dgallium-d3d12-video=enabled` options to the meson build command. Enable support for the VA API (Video-Acceleration API) via the `libva` library to gain an access to graphics hardware acceleration capabilities for video processing. Support accelerated encoding and decoding of the MPEG2, VC-1, H.264/AVC, etc. video codecs.

It is recommended to enable this flag if there is a need to deal with encoding and decoding video files using a compatible GPU, e.g. AMD.

### valgrind
Pass the `-Dvalgrind=auto` (`disabled` if the flag is disabled) option to the meson build command. Build mesa with Valgrind support. Enable some sanitization and additional code to suppress false positive reports from Valgrind in various memory management routines and Kernel calls. This has a performance impact.

This flag should only be enabled if there is a need to run Valgrind tool on the application linked against mesa libraries.

### vdpau
This feature only works with one of the `d3d12`, `r300`, `r600`, `radeonsi` or `nouveau` drivers. Pass the `-Dgallium-vdpau=enabled` option to the meson build command. Enable support for VDPAU (Video Decode and Presentation API) via the `libvdpau` library to access video decoding acceleration and presentation hardware present in modern GPUs. Support accelerated encoding and decoding of the MPEG-1, MPEG-2, MPEG-4 part 2, H.264, VC-1 and DivX video codecs.

It is recommended to enable this flag if there is a need to deal with video files encoding and decoding using a compatible GPU, e.g. Nvidia with Nouveau driver.

### vulkan
This feature only works with one of the `d3d12`, `intel`, `freedreno`, `radeonsi` or `v3d` video drivers. Append the `device-select` value to the `-Dvulkan-layers=true` option and pass it together with the `-Dvulkan-drivers=` option set to a list of supported drivers enabled via `VIDEO_CARDS` to the meson build command. Build and install drivers that utilize Vulkan API - a new generation graphics and compute API that provides high-efficiency, cross-platform access to modern GPUs used in a wide variety of devices. Currently only modern AMD and Intel GPUs are supported.

It is highly recommended to enable this flag if the target system has the AMD or Intel GPU.

### vulkan-overlay
Only works when the `vulkan` flag is enabled. Append the `overlay` value to the `-Dvulkan-layers=` option and pass it to the meson build command. Enable the Vulkan Overlay layer to expose various performance metrics, such as FPS counter, pipeline computations, etc, similar to what Gallium3D "HUD" provides.

The flag can be safely disabled.

### wayland
Append the `wayland` value to the `-Dplatforms=` option and pass it to the Meson build command. Provide an implementation of the EGL API for Wayland clients to draw directly to the framebuffer.

This flag should only be enabled if there is a need to run Wayland server on the target system.

### X
Append the `x11` value to the `-Dplatforms=` option and pass it together with `-Dglx=dri` option to the Meson build script. Enable support for X11 (X Windows System, aka X) platform for various Mesa drivers to allow indirect GLX rendering, DRI or DRM within X server applications (depending on enabled backends and drivers).

This flag should be enabled if the target system runs X11.

### xa
This feature only works with the `freedreno`, `nouveau` or `vmware` driver. Pass the `-Dgallium-xa=enabled` option to the meson build script. Build and install the XA (X.Org Acceleration) state tracker developed by VMWare. It provides versioning support, surface functionality, and YUV blits for textured X-Video, Solid fills without ROP functionality, Copies with format conversion and reinterpretation but without ROP, Xrender-type compositing for general acceleration. It is primarily designed for use by the `vmwgfx` on VMware-virtualized guest operating systems. The Freedreno driver uses XA for accelerating 2D with open-source, reverse-engineered Qualcomm graphics driver.

This flag should only be enabled if the target system runs inside of VMWare machine or runs on Adreno GPU with Freedreno driver.

### zink
Append `zink` to the `-Dgallium-drivers=` option and pass it to the meson build script. Build and install the Zink Gallium driver that emits Vulkan API calls instead of targeting a specific GPU architecture. This can be used to get full desktop OpenGL support on devices that only support Vulkan. This is a very early stage development.

This flag should normally be disabled.

### zstd
Pass the `-Dzstd=enabled` option to the meson build script. Use the `libzstd` library to compress the shader cache using the ZSTD compression algorithm instead of the ZLIB, which is both faster and provides better compression.

This flag can be safely disabled.
