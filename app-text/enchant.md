# app-text/enchant

### aspell
Pass the `--enable-aspell` option to the configure script. Enable Aspell spell-checking backend that uses the `libaspell` library.

This flag should normally be disabled, even though Aspell is a bit more smarter with suggestions, but it is outdated and unmaintained.

### hunspell
Pass the `--enable-myspell` option to the configure script. Enable Hunspell (formerly Myspell) spell-checking backend that uses the `libhunspell` library.

This flag should normally be enabled, because Hunspell is widespread and well supported library.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libenchant` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Execute the `make check` command after the main build is completed to run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled, as these tests are mainly useful for the testers, developers or the Gentoo team.
