# media-gfx/graphite2

### perl
Prepare environment for the configure script to find an appropriate version of Perl files. Patch Perl build script to fix linking issues. Build and install the `Text::Graphite2` and the `Text::Gr2` Perl modules that provide `libgraphite2` Perl bindings.

It is safe to disable this flag.

### test
Prepare a Python environment to properly run the tests. Execute a `ctest` command after the main build is completed. Run a test suite provided with the source code (including Perl module tests if `perl` flag is enabled). When disabled, patch the `CMakeLists.txt` file to exclude `tests` directory from being built to save some time.

This flag should normally be disabled as it is mainly used by the Gentoo team, developers and testers.
