# sci-libs/gsl

### cblas-external
Gentoo uses a patch that allows allows GSL to use external BLAS library. When this flag is enabled, portage will pass the `--with-cblas-external` option to the configure to allow using the external implementation of C BLAS library provided by the [virtual/cblas](../virtual/cblas.md) package.

This flag can be safely disabled.

### deprecated
By default, deprecated functions and enums are disabled at compile time. When this flag is enabled, patch the `configure.ac` script to re-enable them.

It is recommended to disable this flag unless there is a need to use one of the deprecated functions.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libgsl` and `libgslcblas` libraries.

This flag should only ever be enabled if there is a need for the static libraries.
