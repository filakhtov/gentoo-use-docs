# sys-libs/libxcrypt

### compat
Normally, when this flag is disabled, only the `libcrypt.so.2` will be installed, which does not contain obsolete API functions and is not compatible with glibc's supplied `libcrypt`. When this flag is enabled, run the configure script once again with the `--enable-obsolete-api=yes`, `--disable-static` and `--disable-xcrypt-compat-files` arguments, then build and install the binary-comaptible `libcrypt.so.1`.

This flag is currently required by the Gentoo system, because some of the obsolete APIs are still in use in different applications.

### split-usr
Install `libxcrypt` libraries into the root `/libXX` directory, instead of the `/usr/libXX`, so it will be available during the early boot on systems that use separate `/usr` partition.

This flag can be safely disabled on systems that don't have separate `/usr` partition.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libcrypt` library. This only applies for builds with `--enable-obsolete-api=no`, even if the `compat` flag is enabled.

This flag should only ever be enabled if there is an explicit need for the static libraries.

### system
Install the resulting libraries into the `/libXX/libcrypt.*` (or `/usr/libXX/libcrypt.*`) directory, instead of the `/libXX/xcrypt/libcrypt.*`, so it will be default system-wide library to link against, overriding the `libcrypt` provided by the [sys-libs/glibc](../sys-libs/glibc.md) package.

This flag should be enabled, as `libxcrypt` is a preferred library implementation.

### test
Execute the `make check` command (twice if the `compat` flag is enabled to test both variants) after the main build is completed to run the test suite provided with the source code and check for any regressions.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
