# media-libs/libplacebo

### glslang
Only works if the `shaderc` flag is disabled. Pass the `-Dglslang=enabled` option to the meson build script. Use the `glslang` - Khronos-reference front-end compiler to generate SPIR-V (Standard Portable Intermediate Representation) from GLSL (OpenGL Shading Language) code.

It is safe to disable this flag.

### lcms
Pass the `-Dlcms=enabled` option to the meson build script. Enable support for LittleCMS 2 color management engine to properly apply color profiles during rendering.

This flag can be disabled if there is no need to deal with color profiles.

### llvm-libunwind
Only works if the `unwind` flag is enabled. Pull in the [sys-libs/llvm-libunwind](../sys-libs/llvm-libunwind.md) package as a dependency instead of using the default [sys-libs/libunwind](../sys-libs/libunwind.md). See the `unwind` flag for more information.

It is safe to disable this flag.

### opengl
Pass the `-Dopengl=enabled` and `-Dgl-proc-addr=enabled` options to the meson build script. Enable support for the OpenGL-based renderer and the built-in OpenGL loader.

This flag can be safely disabled.

### shaderc
Pass the `-Dshaderc=enabled` and `-Dglslang=disabled` (even if the `glslang` flag is enabled) options to the meson build script. Use Google's `shaderc` compiler to generate SPIR-V (Standard Portable Intermediate Representation) from GLSL (OpenGL Shading Language) code.

It is safe to disable this flag.

### test
Pass the `-Dtests=true` option to the meson build script. Build the test suite provided with the source code. Run the `meson test` command after the main build is completed to run the tests and check for any regressions. This will exentend the overall build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.

### unwind
Pass the `-Dunwind=enabled` option to the meson build script. Use the `libunwind` library to print stack traces caused by runtime errors.

It is safe to disable this flag.

### vulkan
Requires `glslang` or `shaderc` flags to be enabled. Pass the `-Dvulkan=enabled` and `-Dvk-proc-addr=enabled` options to the meson build script. Enable support for Vulkan-based renderer and link directly against the `vkGetInstanceProcAddr` loader from the `libvulkan` library to enable support for Vulkan layers.

This flag can be safely disabled if there is no need to use Vulkan-based APIs.

### xxhash
Pass the `-Dxxhash=enabled` option to the meson build script. Link against the `libxxhash` library to use a faster replacement for the internal SipHash implementation.

It is safe to disable this flag.
