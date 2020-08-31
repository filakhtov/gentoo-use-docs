# gnome-extra/gnome-calculator

### introspection
Generate and install the `GCalc-1.gir` GIR metadata file to provide dynamic bindings for the `libgcalc` library to languages other than C using the GObject Introspection framework. Pass the `-Ddisable-introspection=true` option to the meson build command when this flag is disabled and avoid installation of this GIR metadata file.

It is safe to disable the flag.

### test
Pass the `-Dui-tests=true` option to the meson build command. Start a new Xvfb session and execute the `meson test` command after the main build is completed to execute the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, as these tests are primarily useful for the developers, testers and maintainers.
