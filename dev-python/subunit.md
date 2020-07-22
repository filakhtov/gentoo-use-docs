# dev-python/subunit

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libsubunit` and `libcppunit_subunit` libraries.

This flag should only be enabled if there is a need for static libraries.

### test
Execute the `python -m testtools.run all_tests.test_suite` command for each active Python implementation after the main build is completed to run the test suite provided with the source code and check for any regressions.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
