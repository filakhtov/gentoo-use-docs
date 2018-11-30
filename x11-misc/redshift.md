# x11-misc/redshift

### ayatana
Pull in the [dev-libs/libappindicator](../dev-libs/libappindicator.md) package as a dependency. Redshift uses the GObject Introspection framework to integrate with Ubuntu notification system, aka Ayatana.

This flag should be enabled if the target system runs the Ubuntu Unity desktop environment.

### geoclue
Pass the `--enable-geoclue2` option to the configure script. Use the `libgeoclue-2` library to automatically detect geolocation based on GPS, 3G, WiFi, GeoIP, etc and pre-populate latitude and longitude settings appropriately.

It is safe to disable the flag, however manual location configuration will be required.

### gtk
Pass the `--enable-gui` option to the configure script. Build and install GTK+ based user interface applet for Redshift, written in Python. This applet allows to quickly enable and disable color filtering and provides information about the current status.

This flag should be enabled if there is a need for GUI.

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to provide an ability to translate programs messages and interface at runtime, based on the system locale settings.

This flag can be safely disabled, unless there is a need to use Redshift in a non-English language.
