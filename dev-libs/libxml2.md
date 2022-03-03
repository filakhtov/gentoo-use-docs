# dev-libs/libxml2

### debug
Passes the `--with-run-debug` option to the configure script. The `--with-debug` is not affected and is enabled by default (See [Gentoo bug #100898](https://bugs.gentoo.org/100898) for details).

Provides an ability to obtain and display debug information for XML document, nodes, attributes, etc.

This flag can be safely disabled.

### examples
Normally the ebuild is removing example source code files that are provided with the package from the installation image. Enabling this flag will preserve example files and install them into a `/usr/share/doc/libxml2-<VERSION>/examples` and a `/usr/share/doc/libxml2-<VERSION>/python/examples` directories.

It is safe to disable the flag.

### icu
This flag passes the `--with-icu` option to the configure script. By default, a limited set of the character set encodings is supported. Everything else has to be converted to the UTF-8 before being passed to the parser.

It is safe to disable the flag as it is only required for dealing with XML documents encoded with unusual character sets.

### lzma
The flag passes the `--with-lzma` option to the configure script. This provides support for a transparent LZMA compression at an I/O layer. E.g.  tools provided with the library will be able to process compressed XML (`.xml.lzma`) files directly, without prior decompression.

This flag can be safely disabled unless there is a need for a compressed input or output.

### python
Builds Python bindings for `libxml2`. It is done by separately invoking the `configure` script with the `--with-python` flag and the `make` command for every enabled Python target.

The flag can be safely disabled unless there is a need to run Python scripts that are dependent on the `libxml2` Python module.

### readline
This flag passes the `--with-readline` and the `--with-history` options to the configure script. Provides a support for a history in the `xmllint` shell.

The flag can safely be disabled. It might be useful for people who deal with `xmllint` shell.

### static-libs
Passes the `--enable-static` option to the configure script. This will produce statically linked libraries.

This flag should normally be disabled and might only be necessary for certain developers.

### test
Execute the test suite provided with the library by calling the `make check` command when the main build is completed to check for any regressions. If `python` flag is enabled, additionally execute Python bindings related test suite for every enabled Python target by running a `make test` command for each enabled Python target. This will extend the build time.

This flag should be disabled. It is primarily oriented towards the maintainers, developers and testers.
