# dev-libs/libpwquality

### pam
Pass the `--enable-pam` option to the configure script. Build and install the `pam_pwquality` PAM module to perform strength-checking for passwords that was originaly based on `pam_cracklib` module and is backwards compatible with its options.

It is safe to disable the flag.

### python
Pass the `--enable-python-bindings` option to the configure script. Build and install the `pwquality` Python module for every active Python implementation to provide bindings for the `libpwquality` library.

This flag should be enabled if there is a need for the `pwquality` module.

### split-usr
This flag does nothing.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libpwquality` library. Move static library from the `/lib` to the `/usr/lib` directory where non-static library resides before installing.

This flag should only be enabled if there is an explicit need for the static library.
