# media-video/totem

### debug
Pass the `--enable-debug=yes` option to the configure script. Disable compiler optimizations and build libraries and binaries with debugging symbols included.

This flag only be used for debugging purposes and should be disabled otherwise.

### introspection
Pass the `--enable-introspection` to the configure script. Generate and install the `Totem-1.0.gir` and `Gd-1.0.gir` GIR metadata files to provide dynamic bindings for the `libtotem` and `libgd` libraries respectively to languages other than C, using the GObject Introspection framework.

It is safe to disable the flag.

### lirc
Append the `lirc` value to the `--with-plugins` option that is passed to the configure script. Build and install the `Infrared Remote Control` plugin that allows to control playback using the infrared remote control over the LIRC (Linux Infrared Remote Control) subsystem.

This flag should normally be disabled, unless there is a need to use an infrared remote control.

### nautilus
Append the `save-file` value to the `--with-plugins` option and pass it together with the `--enable-nautilus` option to the configure script. Build and install the `Save Copy` plugin that is used to save a copy of the currently playing movie. Build and install the `libtotem-properties-page` library that provides an ability to display information about video files in a file properties dialog on the `Video/Audio` tab of the Nautilus file manager, including resolution, duration, framerate, etc.

This flag should only be enabled if the target system uses Nautilus file manager and additional properties integration is necessary.

### python
Append the `dbusservice`, `pythonconsole` and `opensubtitles` values to the `--with-plugins` option that is passed to the configure script. Build and install three additional Python-based plugins: the `MPRIS D-Bus Interface` to send notifications of currently-playing videos over D-Bus and allow to control playback using the MPRIS (Media Player Remote Interfacing Specification) D-Bus interface, the `Subtitle Downloader` to look for and download subtitles for the currently playing movie on the OpenSubtitles network and the `Python Console` - an interactive Python console to control playback and plugins.

It is safe to disable the flag if none of these plugins are needed.

### test
Execute the `make check` command after the main build is completed. Run the test suite provided with the source code to check for regressions. This will extend the build time.

This flag should normally be disabled as it is only useful for maintainers, developers and testers.
