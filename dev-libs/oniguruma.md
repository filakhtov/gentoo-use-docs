# dev-libs/oniguruma

### crnl-as-line-terminator
Pass the `--enable-crnl-as-line-terminator` option to the configure script. Enable support for CR (carret return) + NL (new line, aka LN - line feed) line terminator that are primarily used on Windows platform.

This flag should normally be disabled, moreover the configure option is marked as deprecated in the latest version of the library.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libonig` library.

This flag should normally be disabled, unless there is an explicit need for the static library.
