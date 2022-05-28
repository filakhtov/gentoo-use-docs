# dev-python/pygobject

### cairo
Pass the `-Dpycairo=enabled` (`disabled` if the flag is disabled) option to the meson build command. Provide special cairo integration through the Pycairo module despite cairo library itself not being a GObject based. Provide an ability to load Cairo interface using the `gi.require_foreign("cairo")` call.

This flag should only be enabled if there is a need to use Python GObject bindings for the Cairo library.

### examples
Install additional example files into the `/usr/share/doc/pygobject-<VERSION>/examples` directory. This includes a demo Cairo project written in Python and based on the C code from the Cairo library itself.

It is safe to disable the flag.

### test
Pass the `-Dtests=true` (`false` when the flag is disabled) option to the meson build command. Build the test suite provided with the source code. After the main build is completed, start a new Xvfb session and execute the `meson test` command for each enabled Python implementation to check for regressions. This will extend the build time.

This flag should normally be disabled as it is primarily used by the Gentoo team, developers and testers.
