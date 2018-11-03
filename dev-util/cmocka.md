# dev-util/cmocka

### doc
Execute the `doxygen` command from the `doc` directory to generate documentation in the HTML and latex formats and install it into the `/usr/share/doc/cmocka-<VERSION>` directory. Documentation include man pages with API description, reference and usage manuals for developers, etc.

It is safe to disable the flag.

### static-libs
Pass the `-DWITH_STATIC_LIB=true` option to the `cmake` command. Build and install a statically linked version of the `libcmocka` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Pass the `-DUNIT_TESTING=true` option to the `cmake` script. Build the test suite provided with the source code and run the `ctest` command after the main build is completed to execute it.

This flag should normally be disabled as these test are primarily used by the Gentoo team, testers or developers.
