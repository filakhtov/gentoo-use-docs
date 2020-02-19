# net-libs/libproxy

### gnome
Pass the `-DWITH_GNOME3=yes` option to the CMake command. Build and install the `pxgsettings` binary that is used to query GSettings configuration backend for proxy settings. When disabled, build and install the `pxgconf` instead to query GConf backend (but only if GConf library is found).

This flag should be enabled if the target system is running a GNOME 3 based desktop environment.

### kde
Pass the `-DWITH_KDE=yes` option to the CMake command. Build and install module to read proxy settings from KDE4/KF5 using the `kreadconfig` or `kreadconfig5` tools.

This flag should be enabled if the target system is running a KDE based desktop environment.

### mono
Pass the `-DWITH_DOTNET=yes` and the `-DGMCS_EXECUTABLE="/usr/bin/mcs"` options to the CMake command. Build and install `libproxy-sharp` library - C# bindings for the `libproxy` library to be used with Mono-based applications for automatic proxy configuration management.

This flag should only be enabled if there is a need to use `libproxy` with C# applications.

### networkmanager
Pass the `-DWITH_NM=yes` option to the CMake command. Build and install the `network_networkmanager` library - a libproxy module to read information about a network connections change from NetworkManager.

This flag should be enabled if target system uses NetworkManager for network configuration.

### spidermonkey
Pass the `-DWITH_MOZJS` option to the CMake command. Build and install the `pacrunner_mozjs` library - a `libproxy` module that contains the plugin to allow libproxy to interpret PAC (Proxy Auto-Configuration) files using mozjs.

It is safe to disable the flag.

### test
Pass the `-DBUILD_TESTING=yes` option to the CMake command. Build test suite provided with the source code and execute the `ctest` command after the main build is completed to run it. This will extend a build time.

This flag should normally be disabled as it is mainly useful for testers, developers or the Gentoo team.

### webkit
Pass the `-DWITH_WEBKIT3=yes` option to the CMake command. Build and install the `pacrunner_webkit` library - a `libproxy` module that contains the plugin to allow libproxy to interpret PAC (Proxy Auto-Configuration) files using GTK+ webkit engine.

It is safe to disable the flag.
