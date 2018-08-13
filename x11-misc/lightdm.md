# x11-misc/lightdm

### audit
Pass the `--enable-libaudit` option to the configure script. Use the `libaudit` library to report login and logout events via the Kernel Auditing Subsystem.

It is safe to disable the flag.

### gnome
Pass the `--with-user-session=gnome` option to the configure script. Set the default login session to GNOME.

This flag should be enabled if the target system to be used with the GNOME desktop environment.

### introspection
Pass the `--enable-introspection` option to the configure script. Build and install the `liblightdm-gobject-1` library - a GObject client library and generate the `LightDM-1.gir` GIR metadata file to provide dynamic bindings for the `liblightdm` library to languages other than C using the GObject introspection.

It is safe to disable the flag.

### qt5
Append the `-std=c++11` option to the `CXXFLAGS` variable for a duration of the build. Pass the `--enable-liblightdm-qt5` option to the configure script. Build LightDM with support for the Qt 5 toolkit.

This flag should be enabled if the LightDM to be used with the Qt-based desktop environment, e.g. KDE.
