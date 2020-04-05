# dev-libs/libevdev

### doc
Pass the `-Ddocumentation=enabled` (`disabled` if the flag is off) option to the meson build script. Generate additional documentation in the HTML format using the Doxygen tool and install it into the `/usr/share/doc/libevdev-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Pass the `-Dtests=enabled` (`disabled` when this flag is off) option to the meson build script. Build the test suite and run the `meson test` command when the build is completed to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag should normally be disabled, because the test suite is primarily useful for developers, maintainers and testers, not the end users.
