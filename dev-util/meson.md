# dev-util/meson

### test
Prepare an environment and execute the `run_test.py` script for every active Python implementation from the source tree after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled as it is mainly used by the maintainers, testers and developers.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
