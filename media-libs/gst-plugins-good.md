# media-libs/gst-plugins-good

### nls
Pass the `-Dnls=enabled` option to the Meson build script. Use the Gettext library to provide an ability to translate programs messages at runtime into different languages based on system locale settings.

It is safe to disable the flag.

### orc
Pull in the [dev-lang/orc](../dev-lang/orc.md) package as a dependency. The `liborc` library provides ORC (Optimized inner loops Runtime Compiler) that is used to map to SIMD instructions on various architectures for hardware acceleration.

This flag should normally be enabled to utilize hadware acceleration, howevere there is no support for the ARM64/AArch64 architecture at the moment.

### test
Pass the `-Dtests=enabled` option to the Meson build script. Build the test suite provided with the source code and execute the `ninja test` command inside of the virtual Xvfb session to run it after the main build is completed. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.
