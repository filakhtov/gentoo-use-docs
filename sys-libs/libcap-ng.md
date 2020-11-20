# sys-libs/libcap-ng

### python
For each enabled Python target execute the configure script and pass the `--with-python` and `--with-python3` options to the configure script. Execute the `make` command from the `bindings/python` directory of the source tree for each enabled Python target to build the `capng` module - Python bindings for the `libcap-ng` library.

This flag should only be enabled if there is a need to run Python scripts that use the `capng` module.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libcap-ng` library.

This flag should only be enabled if there is an explicit need for the static library.
