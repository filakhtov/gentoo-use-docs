# x11-wm/muffin

### introspection
Pass a `--enable-introspection` option to a configure script. Generate and install a `Meta-Muffin.0.gir` GIR metadata file to provide dynamic bindings for a `libmuffin` library to languages other than C using a GObject Introspection infrastructure.

It is safe to disable the flag.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.

### xinerama
Pass a `--enable-xinerama` option to a configure script. Use a Xinerama API to query a multi-monitor geometry and provide a proper window positioning and sizing for screens that are configured using the Xinerama X extension.

This flag should normally be disabled, because Xinerama is an outdated way of doing multi-monitor setup and is nowadays replaced by the Xrandr extension.
