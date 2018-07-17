# sys-libs/cracklib

### nls
Pass the `--enable-nls` option to the configure script. Enable an ability to translate program messages into various languages. Install localization files.

This flag can be safely disabled unless there is a need to use non-English languages.

### python
Run a `setup.py` from a `python` source code directory for every enabled python target. Build and install Python bindings for a `libcrack` library. Provide a `cracklib` Python module.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libcrack` library.

This flag should be normally disabled, unless there is an explicit need for the static library.

### zlib
Export an `ac_cv_header_zlib_h=yes` and an `ac_cv_search_gzopen=-lz` variables for the configure script. Provide a transparent support for Gzip compressed dictionary files.

It is safe to disable the flag.
