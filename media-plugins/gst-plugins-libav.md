# media-plugins/gst-plugins-libav

### libav
Allow this plugin to be built on systems that use Libav instead of FFmpeg by using internal FFmpeg copy provided with the source code. When disabled, pass the `--with-system-libav` to use the system-wide version of the FFmpeg library.

This flag must be enabled on systems that use the Libav libraries over the FFmpeg ones, and should be disabled otherwise.

### orc
Pass the `--enable-orc` option to the configure script. Use the `liborc` library (Optimized Inner Loops Runtime Compiler) to access SIMD instructions and other optimizations and utilize hardware acceleration. When disabled, slower unoptimized backup code will be used instead.

It is generally recommended to enable this flag on platforms that support AltiVec, MMX/MMX2 or 3DNOW instructions to improve performance.
