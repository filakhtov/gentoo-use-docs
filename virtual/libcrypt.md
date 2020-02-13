# virtual/libcrypt

### static-libs
Ensure that the `static-libs` flag is enabled for [sys-libs/glibc](../sys-libs/glibc.md) package, but only if the version higher than `2.30-r2`, because older versions always provide a static version of the `libcrypt` library.

This flag can be safely disabled.
