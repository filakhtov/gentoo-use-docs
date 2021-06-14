# app-crypt/libb2

### native-cflags
Pass the `--enable-native` option to the configure script. Build a library optimized for the CPU found at compile time on systems that support it. Ensure that custom `CFLAGS` variable set via the Portage configuration isn't used during the build.

This flag can be safely disabled.

### openmp
This flag requires an OpenMP-enabled compiler. Pass the `--enable-openmp` option to the configure script. Append the `-fopenmp` option to the `CFLAGS` variable for the duration of the build. Use the OpenMP library to enable support for parallelized hash computations.

This flag can be enabled to improve performance via parallelization.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libb2` library.

This flag should only ever be enabled if there is an explicit need for the statically linked library.
