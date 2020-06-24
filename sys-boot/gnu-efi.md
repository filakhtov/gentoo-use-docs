# sys-boot/gnu-efi

### custom-cflags
When disabled, all user supplied `CFLAGS`, `CPPFLAGS` and `LDFLAGS` will be ignored. When enabled, some flags, known to be causing issues, will be filtered from the user supplied compiler flags and the rest will be used during compilation.

This flag should normally be disabled, because custom flags known to be causing issues and should be handled with extra care.
