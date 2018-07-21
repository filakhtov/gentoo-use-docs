# app-arch/unzip

### bzip2
Patch a `unix/Makefile` file to uncomment a `L_BZ2` variable with `-lbz2` value to pass it as a linker option. Append a `-DUSE_BZIP2` option to the `CPPFLAGS` variable for a duration of the build. Provide an ability to decompress an archive in a Bzip2 algorithm using a `libbz2` library.

It is safe to disable the flag.

### natspec
Apply a patch to use a `natspec` library for decoding non-ASCII filenames in non-Unicode ZIP archives created on the Windows platform using one of its codepages.

This flag should be enabled if there is a need to deal with ZIP files created on Windows platform, otherwise it is safe to disable.

### unicode
Append a `-DUNICODE_SUPPORT`, `-DUNICODE_WCHAR`, `-DUTF8_MAYBE_NATIVE`, and a `-DUSE_ICONV_MAPPING` options to the `CPPFLAGS` variable for a duration of the build. Provide an ability to convert non-ASCII Unicode characters into escape sequences or ignore them via the `-U` and the `-UU` runtime options.

The flag should be enabled if there is a need to use ZIP files that contain Unicode filenames and otherwise can be safely disabled.
