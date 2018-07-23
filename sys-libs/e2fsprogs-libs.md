# sys-libs/e2fsprogs-libs

### nls
Pass the `--enable-nls` option to the configure script. Provide an ability to translate programs messages into different languages based on the system locale settings.

This flag should be enabled if there is a need to use a non-English language.

### static-libs
Statically linked versions of `libcom_err` and `libss` libraries are built by default, so this flag does nothing if enabled. When disabled, remove these statically linked libraries from an image before installation.

This flag should only be enabled if there is a need for the static libraries.
