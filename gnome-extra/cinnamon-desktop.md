# gnome-extra/cinnamon-desktop

### introspection
Pull in the [dev-libs/gobject-introspection](../dev-libs/gobject-introspection.md) package as a dependency and make sure that the `introspection` flag is enabled for the [x11-libs/gdk-pixbuf](../x11-libs/gdk-pixbuf.md) and [x11-libs/gtk+](../x11-libs/gtk+.md) packages. This is required to generate the `Cvc-1.0.gir`, `CDesktopEnums-3.0.gir` and `CinnamonDesktop-3.0.gir` GIR metadata files to provide dynamic bindings for the languages other than C to the `libcinnamon-desktop` and the `libcvc` libraries.

This flag should be enabled if there is a need for GObject Introspection bindings for the libraries.

### systemd
Install the `cinnamon-desktop.systemd.gschema.override` override file into the `/usr/share/glib-2.0/schemas` directory to change default settings for GSettings database for better integration with the SystemD's logind session manager.

This flag should be enabled for a system that runs SystemD as its init system.
