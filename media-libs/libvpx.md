# media-libs/libvpx

### doc
Pass the `--enable-install-docs` and `--enable-docs` options to the configure script. Use the Doxygen tool to generate documentation in the HTML format and install it into the `/usr/share/docs/libvpx-<version>` directory.

It is safe to disable this flag.

### highbitdepth
Pass the `--enable-vp9-highbitdepth` option to the configure script. Enable support for encoding VP9 videos with high bit depth profiles (10- and 12-bit).

This flag can be safely disabled.

### postproc
Pass the `--enable-postproc` option to the configure script. Enable support for various post-processing filters.

It is safe to disable this flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libvpx` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Pass the `--enable-unit-tests` option to the configure script to build the test suite provided with the source code and execute the `make test` command to run it after the main build is completed and check for any regressions.

This flag should normally be disabled, as it is primarily oriented towards the developers, maintainers and testers.

### threads
Pass the `--enable-multithreaded` option to the configure script. Enable support for multi-threaded encoding and decoding, i.e. using multiple threads to parallelize and speed up these operations.

It is recommended to enable this flag on any modern multi-core system to improve performance.
