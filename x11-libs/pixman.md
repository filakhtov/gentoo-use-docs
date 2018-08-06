# x11-libs/pixman

### altivec
Pass the `--enable-vmx` option to the configure script. Use AltiVec (aka VMX - Vector Multimedia Extension, aka Velocity Engine) SIMD instruction set on supported PowerPC processors to improve image manipulation performance.

It is recommended to enable this flag on PowerPC systems with AltiVec instruction set.

### iwmmxt
Pass the `--arm-iwmmxt` option to the configures script. Provide an ability to utilize iwMMXt (Intel Wireless MMX Technology) SIMD extension on supported ARM processors to improve image manipulation performance.

This flag should be enabled on ARM systems that support `iwMMXt`.

### loongson2f
Pass the `--enable-loongson-mmi` option to the configure script. Enable inline assembly code that uses Loongson MMI (Loongson Multimedia Instructions) SIMD instruction set to improve image manipulation performance on the Loongson platform.

This flag should only be enabled on the Loongson platform.

### neon
Pass the `--enable-arm-neon` option to the configure script. Utilize Advanced SIMD extension (aka NEON, aka MPE - Media Processing Engine) on supported ARM platform to improve image manipulation performance.

It is recommended to enable this flag on ARM platforms with NEON instructions support.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install a statically linked version of the `libpixman` library.

This flag should only be enabled if there is a need for the static library.
