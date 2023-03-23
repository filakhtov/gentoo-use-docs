# app-arch/zstd

### lz4
Pass the `-Dlz4=enabled` option to the meson build script. Use the `liblz4` library to provide an ability to compress and decompress files in the LZ4 format using the `--format=lz4` command line option.

This flag can be safely disabled

### lzma
Pass the `-Dlzma=enabled` option to the meson build script. Use the `liblzma` library to provide an ability to compress and decompress files in the `lzma` format using the `--format=lzma` command line option.

It is safe to disable this flag.

### split-usr
When enabled, built libraries will be installed into the `/lib` directory (instead of usual `/usr/lib`) to make sure that they are available during an early system boot, before additional partitions are mounted.

This flag should be enabled if the system has a separate `/usr` partition and can be safely disabled otherwise.

### static-libs
Pass the `-Ddefault_library=both` (instead of `shared`) option to the meson build script. Build and install a statically linked version of the `libzstd` library.

This flag should only ever be enabled if there is an explicit need for the static library.

### test
Pass the `-Dbin_tests=true` option to the meson build script to build the test suite provided with the source code and execute the `meson test` command after the main build is completed to run it and check for any regressions.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.

### zlib
Pass the `-Dzlib=enabled` option to the meson build script. Use the `libz` library to provide an ability to compress and decompress files in the gzip format using the `--format=gzip` command line option.

It is safe to disable this flag.
