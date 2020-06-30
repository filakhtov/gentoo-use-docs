# media-plugins/gst-plugins-libav

### orc
Pass the `--enable-orc` option to the configure script. Use the `liborc` library (Optimized Inner Loops Runtime Compiler) to access SIMD instructions and other optimizations and utilize hardware acceleration. When disabled, slower unoptimized backup code will be used instead.

It is generally recommended to enable this flag on platforms that support AltiVec, MMX/MMX2 or 3DNOW instructions to improve performance.
