# x11-misc/lightdm

### audit
Pass the `--enable-libaudit` option to the configure script. Use the `libaudit` library to report login and logout events via the Kernel Auditing Subsystem.

It is safe to disable the flag.

### gnome
Pass the `--with-user-session=gnome` option to the configure script. Set the default login session to GNOME.

This flag should be enabled if the target system to be used with the GNOME desktop environment.

### gtk
Pull in the [x11-misc/lightdm-gtk-greeter](../x11-misc/lightdm-gtk-greeter.md) package as a dependency to install GTK greeter for LightDM and set it as a default greeter.

This flag should be enabled if the LightDM to be use with the GTK+-based desktop environment, e.g. Cinnamon, XFCE.

### introspection
Pass the `--enable-introspection` option to the configure script. Build and install the `liblightdm-gobject-1` library - a GObject client library and generate the `LightDM-1.gir` GIR metadata file to provide dynamic bindings for the `liblightdm` library to languages other than C using the GObject introspection.

It is safe to disable the flag.

### non-root
Add the `lightdm` user to the `video` group to be able to run greeter as an unprivileged user.

It is recommended to enable this flag.

### qt5
Append the `-std=c++11` option to the `CXXFLAGS` variable for a duration of the build. Pass the `--enable-liblightdm-qt5` option to the configure script. Build LightDM with support for the Qt 5 toolkit.

This flag should be enabled if the LightDM to be used with the Qt-based desktop environment, e.g. KDE.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Generate and install the `liblightdm-gobject-1.vapi` Vala bindings file for the `liblightdm-gobject-1` library.

It is safe to disable the flag.
