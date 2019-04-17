# x11-libs/libvdpau

### dri
Does nothing when enabled, because DRI support is enabled by default. When disabled, pass the `--disable-dri2` option to the configure script to disable it. Use the DRI2 (Direct Rendering Infrastructure) framework to figure out an appropriate VDPAU driver. If this flag is disabled, driver name should be passed as the `VDPAU_DRIVER`, otherwise the library will fall back to an "nvidia" one.

It is recommended to enable this flag if there is a need to use the VDPAU acceleration with non-Nvidia GPU, otherwise it can be safely disabled.

### doc
Pass the `--enable-documentation` to the configure script. Use the Doxygen tool to extract comments out of the source code, generate API documentation in the HTML format, including object types and data flow description, and install it into the `/usr/share/doc/libvdpau-<VERSION>` directory.

It is safe to disable the flag.

### test
Start a new Xvfb session (Virtual X server environment) and execute the `make check` command inside of it when the main build is completed to run the test suite provided with the source code to check for regressions. This will extend a build time.

This flag should normally be disabled as it is only useful for the developers and maintainers.
