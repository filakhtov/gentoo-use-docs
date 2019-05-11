# net-libs/libpsl

### icu
Only works if the `idn` flag is disabled and is an alternative to it. Pass the `--enable-builtin=libicu` and `--enable-runtime=libicu` options to the configure script. Use the `libicu` library to convert an internationalized domain name from a native encoding to its ASCII representation.

This flag can be disabled if there is no need to deal with internationalized domain names.

### idn
This flag is an alternative to the `icu` flag, but takes precedence over it when enabled. Pass the `--enable-builtin=libidn2` and `--enable-runtime=libidn2` options to the configure script. Use the `libidn2` library to convert an internationalized domain name from a native encoding to its ASCII representation.

This flag should be disabled if the `icu` is preferred, or if there is no need to deal with internationalized domain names.

### man
Pass the `--enable-man` option to the configure script. Generate and install man pages. Man page contains library API and is not really useful for an average user.

It is safe to disable the flag.
