# dev-libs/jsoncpp

### doc
Run the `doxybuild.py` script to generate the HTML documentation from the source code annotations using the Doxygen tool.

This flag can be safely disabled.

### test
Pass the `-Dtests=true` option to the meson build command. Run the `meson test` command after the main build is finished to execute the test suite provided with the source code and check for any regressions. This will extend the overall build time.

The flag should normally be disabled, because it is primarily oriented towards developers, testers and maintainers.
