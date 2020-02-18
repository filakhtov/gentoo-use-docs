# app-arch/snappy

### test
Pass the `-DCMAKE_DISABLE_FIND_PACKAGE_GTest=false` option to the CMake command. Execute the `snappy_unittest` command when the main build is completed to run the test suite provided with the source code and check for regressions. This will extend a build time.

This flag should normally be enabled as these tests are mainly useful for the Gentoo team, testers or developers.
