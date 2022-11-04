# app-arch/zstd

### lz4
Pass the `HAVE_LZ4=1` (`0` if the flag is disabled) variable to the make command. Use the `liblz4` library to provide an ability to compress and decompress files in the LZ4 format using the `--format=lz4` command line option.

It is safe to disable this flag.

### split-usr
When enabled, built libraries will be installed into the `/lib` directory (instead of usual `/usr/lib`) to make sure that they are available during an early system boot, before additional partitions are mounted.

This flag should be enabled if the system has a separate `/usr` partition and can be safely disabled otherwise.

### static-libs
Normally, a statically linked version of the `libzstd` library is built and installed, so when this flag is enabled nothing extra is done. When disabled, the static library will be removed before the package is installed into the system.

This flag should only ever be enabled if there is an explicit need for the static library.
