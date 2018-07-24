# dev-libs/libnatspec

### doc
Documentation is built by default, so this flag does nothing when enabled. If disabled, export an `ac_cv_prog_DOX=no` variable for the configure script. Use Doxygen to generate library API documentation and install it into `/usr/share/doc/libnatspec-<VERSION>` directory.

It is safe to disable the flag.

### python
Pass the `--with-python` option to the configure script. Build and install a `_natspec` Python module - a Python binding for a `libnatspec` library.

This flag should be enabled if there is a need to run Python scripts that require `_natspec` module.
