# libgpg-error

### common-lisp
Pass the `--enable-languages` option to the configure script. Build and install components from `lang` directory of a source code that provide support for programming languages other than C. Currently the only supported is Common Lisp, hence the flag name.

It is safe to disable this flag as it is only necessary for running or developing Common Lisp applications dependent on the `libgpg-error` library.

### nls
Pass the `--enable-nls` option to the configure script. Install a translation and a localization support for messages displayed by the library.

This flag should be enabled if there is a need to display messages in non-English languages. It is safe to disable the flag otherwise.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libgpg-error` library.

This flag should only be enabled if there is an explicit need for this static library, e.g. for development purposes.

### test
Pass the `--enable-tests` option to the configure script. Build the test suite provided with the source code and execute the `make check` command to run it after the main build is completed and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the developers, maintainers and testers.
