# x11-libs/libxkbcommon

### doc
Pass the `-Denable-docs=true` option to the meson build script. Generate and API documentation from the source code annotation in an HTML format using the doxygen tool and install it into `/usr/share/docs/libxkbcommon-<VERSION>/html` directory.

It is safe to disable the flag.

### static-libs
Pass the `-Ddefault_library=both` (instead of `shared`) option to the meson build script. Build and install a statically linked version of the `libxkbcommon` (and `libxkbcommon-x11` if the `X` flag is enabled) library.

This flag should only ever be enabled if there is a need for static libraries.

### test
Start a new Xvfb session and execute the `meson test` command inside of it after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag should normally be disabled as it is mainly useful for maintainers, testers and developers.

### tools
Pass the `-Denable-tools=true` option to the Meson build script. Build and install additional tools, such as `xkbcli`, `compile-keymap`, `compose`, `xkbcli-how-to-type`, `xkbcli-interactive-evdev`, `xkbcli-interactive-x11` (when the `X` flag is enabled) and `xkbcli-interactive-wayland` (if the `wayland` flag is also enabled).

It is safe to disable this flag, if none of these tools are needed.

### wayland
Pass the `-Denable-wayland=true` option to the meson build script. Enable support for interactive debugger for XKB keymaps for Wayland in the `xkbcli` utility.

This flag should normally be disabled.

### X
Pass the `-Denable-x11=true` option to the meson build script. Build and install a `libxkbcommon-x11` library and a `xkbcommon-x11.h` include file. Provide an ability to create and modify keymaps, e.g. change to special symbols when modifier key is pressed via an XKB X11 extension.

It is recommended to enable this flag if there is a need to run an X.Org server.
