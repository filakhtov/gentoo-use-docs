# dev-libs/expat

### examples
Install an example C source code into a `/usr/share/doc/expat-<VERSION>/examples` directory.

This flag should normally disabled, unless there is a need for example files for development purposes.

### static-libs
Pass the `--enable-static` option to the configure script. A build will produce and install statically linked libraries.

It is recommended to disable this flag, unless there is an explicit need for statically liked libraries, e.g. for development purposes.

### test
Pass the `--enable-tests` option to the configure script. Build a test suite provided with the source code and execute the `make check` command after the main build is completed to check for any regressions.

This flag should normally be disabled, because it is primarily oriented towards the developers, maintainers and testers.

### unicode
After doing regular configure, adjust `Makefile` rules to build a `libexpatw.la` library and re-run configure again. Append a `-DXML_UNICODE` compiler flag. Produce and install "wide" library version that supports multi-byte Unicode character sets.

It is recommended to enabled this flag as a multi-byte Unicode is widespread nowadays.
