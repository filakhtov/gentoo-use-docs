# media-libs/libcanberra

### alsa
Pass a `--enable-alsa` option to a configure script. Build and install a `libcanberra-alsa` library - an ALSA-based (Advanced Linux Sound Architecture) backend for event sounds generation.

This flag should be enabled if a primary sound system for the target system is ALSA.

### gnome
Pull in a [gnome-base/dconf](../gnome-base/dconf.md) and a [gnome-base/gsettings-desktop-schemas](../gnome-base/gsettings-desktop-schemas.md) packages as a dependency to integrate the package with the GNOME desktop environment.

This flag should only be enabled if there is a need to run a GNOME-based desktop environment.

### gstreamer
Pass a `--enable-gstreamer` option to a configure script. Build and install a `libcanberra-gstreamer` library - a GStreamer backend for event sounds generation.

It is recommended to disable this flag and use other backend, such as ALSA or Pulseaudio if appropriate.

### gtk
Pass a `--enable-gtk` option to a configure script. Build and install a `libcanberra-gtk` library that provides glue code to make it easier to use a `libcanberra` library from Gtk+ applications, and a `libcanberra-gtk-module` library - a Gtk+ module that uses the `libcanberra-gtk` library to trigger input feedback event sounds. Also build and install a `canberra-gtk-play` binary that plays sound events that are specified by the XDG Sound Theme and Name Specification.

This flag should be enabled if there is a need to use the library with Gtk+ apps.

### gtk3
Pass a `--enable-gtk3` option to a configure script. Build and install a `libcanberra-gtk3` library that provides glue code to make it easier to use the `libcanberra` library with Gtk+3 applications, and a `libcanberra-gtk3-module` library - a Gtk+3 module that uses the `libcanberra-gtk3` library to trigger input feedback event sounds. Also build and install a `canberra-gtk-play` binary that plays sound events that are specified by the XDG Sound Theme and Name Specification.

This flag should be enabled if there is a need to use the library with Gtk+3 apps.

### oss
Pass a `--enable-oss` option to a configure script. Build and install a `libcanberra-oss` library - an OSS-based (Open Sound System) backend for event sounds generation.

This flag should only ever be enabled if the only available sound system is OSS.

### pulseaudio
Pass a `--enable-pulse` option to a configure script. Build and install a `libcanberra-pulse` library - a PulseAudio-based backend for event sounds generation.

This flag should be enabled if a primary sound system for the target system is PulseAudio.

### sound
Pull in a [x11-themes/sound-theme-freedesktop](../x11-themes/sound-theme-freedesktop.md) package as a dependency to provide sounds for different desktop events.

This flag should be enabled if there is a need for playing login, logout and other event sounds.

### tdb
Pass a `--enable-tdb` option to a configure script. Use a Samba's tdb trivial database to provide a lookup cache for system sounds.

It is safe to disable the flag.

### udev
Pass a `--enable-udev` option to a configure script. Build and install a `canberra-boot` binary that uses an ALSA-based backend to play a startup, reboot or shutdown sounds at an appropriate time from init service.

This flag is safe to disable.
