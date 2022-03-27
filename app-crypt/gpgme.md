# app-crypt/gpgme

### cxx
Append the `cpp` value to the `--enable-languages` option that is passed to the configure script. Build and install the `libgpgmepp` library that contains a C++ wrapper for the GpgME (GnuPG Made Easy) library.

This flag should be enabled if there is a need to use the GpgME library with a C++ project.

### common-lisp
Append the `cl` value to the `--enable-languages` option that is passed to the configure script. Build and install the `gpgme.asd`, `gpgme-package.lisp` and `gpgme.lisp` Common Lisp binding files. Provide an ability to use GpgME library with the Common Lisp language.

This flag should only be enabled if there is a need to use GpgME with Common Lisp programs.

### python
Prepare python environment and execute the `make prepare`, `make` and `make` install commands from the `lang/python` source subdirectory. Install a `gpg` Python module that offers two interfaces, one is a high-level, curated, and idiomatic interface that is implemented as a shim on top of the low-level interface automatically created using SWIG (Simplified Wrapper and Interface Generator).

This flag should only be enabled if there is a need to use the `gpg` module in Python scripts.

### qt5
Append the `qt` value to the `--enable-languages` option that is passed to the configure script. Build and install the `libqgpgme` library that provides a very high level Qt API around GpgMEpp library.

This flag should be enabled if there is a need for the Qt wrapper library.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libgpgme` library (and the `libgpgmepp` library if the `cxx` flag is enabled).

This flag should only be enabled if there is an explicit need for the static libraries.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
