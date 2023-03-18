# net-libs/libpsl

### icu
Only works if the `idn` flag is disabled and is an alternative to it. Pass the `-Dbuiltin=true` and `-Druntime=libicu` options to the meson build script. Use the `libicu` library to convert an internationalized domain name from a native encoding to its ASCII representation.

This flag can be disabled if there is no need to deal with internationalized domain names.

### idn
This flag is an alternative to the `icu` flag, but takes precedence over it when enabled. Pass the `-Dbuiltin=true` and `-Druntime=libidn2` options to the meson build script. Use the `libidn2` library to convert an internationalized domain name from a native encoding to its ASCII representation.

This flag should be disabled if the `icu` is preferred, or if there is no need to deal with internationalized domain names.
