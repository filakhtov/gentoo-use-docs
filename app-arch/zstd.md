# app-arch/zstd

### lz4
Pass the `HAVE_LZ4=1` (`0` if the flag is disabled) variable to the make command. Use the `liblz4` library to provide an ability to compress and decompress files in the LZ4 format using the `--format=lz4` command line option.

It is safe to disable this flag.

### static-libs
Normally, a statically linked version of the `libzstd` library is built and installed, so when this flag is enabled nothing extra is done. When disabled, the static library will be removed before the package is installed into the system.

This flag should only ever be enabled if there is an explicit need for the static library.

### threads
Append the `-pthread` option to the compiler flags (`CFLAGS`, `CXXFLAGS`, etc). Execute the `make libzstd-mt` command to build the multi-threaded library that provides advanced API that can be used to compress data using mulitple threads in parallel to speed-up the process.

It is safe to disable this flag, but it can improve performance on multi-processor systems.
