# dev-libs/appstream

### apt
Pass the `-Dapt-support=true` option to the Meson build script. Enable integration with APT package manager on Debian.

This flag should normally be disabled on Gentoo systems.

### doc
Pass the `-Dinstall-docs=true` option to the Meson build script. Install documentation for API and specification in the HTML format.

It is safe to disable this flag.

### introspection
Pass the `-Dgir=true` option to the Meson build script. Generate and install the `AppStream-1.0.gir` GIR metadata file to provide dynamic bindings for the `libappstream` library to languages other than C using the GObject Introspection framework.

This flag can be safely disabled.

### qt5
Pass the `-Dqt=true` option to the Meson build script. Build and install the `libAppStreamQt` library which provides a Qt5 interface for accessing AppStream.

It is safe to disable the flag.

### test
Test code is built and executed by default and the test suite provided with the source code is run to check for any regressions. When this flag is disabled, the `meson.build` script will be patched to prevent this from happening.

This flag should normally be disabled, because it is primarily used by the developers, maintainers and testers.
