# media-libs/gst-plugins-good

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to provide an ability to translate programs messages at runtime into different languages based on system locale settings.

It is safe to disable the flag.

### orc
Pull in the [dev-lang/orc](../dev-lang/orc.md) package as a dependency. The `liborc` library provides ORC (Optimized inner loops Runtime Compiler) that is used to map to SIMD instructions on various architectures for hardware acceleration.

This flag should normally be enabled to utilize hadware acceleration, howevere there is no support for the ARM64/AArch64 architecture at the moment.
