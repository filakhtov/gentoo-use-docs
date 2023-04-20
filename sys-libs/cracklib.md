# sys-libs/cracklib

### nls
Pass the `--enable-nls` option to the configure script. Enable an ability to translate program messages into various languages. Install localization files.

This flag can be safely disabled unless there is a need to use non-English languages.

### python
Run a `setup.py` from a `python` source code directory for every enabled python target. Build and install Python bindings for a `libcrack` library. Provide a `cracklib` Python module.

It is safe to disable the flag.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libcrack` library.

This flag should be normally disabled, unless there is an explicit need for the static library.

### test
Use the Python's `unittest` module to run the test suite provided with the source code after the main build is completed and check for any regressions. This will extend the build time.

This flag should normally be disabled, because the test suite is primarily oriented towards the developers, maintainers and testers.

### zlib
Export an `ac_cv_header_zlib_h=yes` and an `ac_cv_search_gzopen=-lz` variables for the configure script. Provide a transparent support for Gzip compressed dictionary files.

It is safe to disable the flag.
