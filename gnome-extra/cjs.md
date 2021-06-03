# gnome-extra/cjs

### cairo
Pass the `-Dcairo=enabled` option to the meson build script. Integrate with the Cairo graphics library to provide an ability to produce 2d graphics, load, manipulate, display and draw images, render text and so on, using the JavaScript language.

This flag should be enabled if there is a need to run Cjs scripts that draw images using the Cairo library, which is what Cinnamon ecosystem does a lot.

### examples
Install additional code examples written in the JavaScript language into the `/usr/share/doc/cjs-<VERSION>/examples` directory. Examples show how to create Gtk+ window with simple button, render a scene using Clutter, access translations using Gettext and so on.

It is safe to disable the flag.

### gtk
This flag is used only if the `test` flag is also enabled. Pull in the [x11-libs/gtk+](../x11-libs/gtk+.md) package as a dependency to provide an ability for tests to run the tests that use GTK+ toolkit.

This flag should normally be disabled.

### readline
Pass the `-Dreadline=enabled` option to the `meson` build script. Use the readline library to provide rich user input in the interactive shell and debugger.

It is safe to disable this flag.

### sysprof
Pass the `-Dprofiler=enabled` option to the `meson` build script. Enable integration with sysprof profiler to capture and send various runtime metrics, including JavaScript code call stacks.

This flag should only be enabled if there is a need to use sysprof profiler on CJS.

### test
Pass the `-Dskip_dbus_tests=false` (`true` if the flag is disabled) and `-Dskip_gtk_tests=false` (`true` when this flag is disabled) to build additional test code. Start a new Xvfb session and execute the `meson test` command inside of it when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend a build time.

This flag should normally be disabled as it is primarily used by the maintainers, testers and developers.
