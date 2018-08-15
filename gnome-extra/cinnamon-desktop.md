# gnome-extra/cinnamon-desktop

### introspection
Pass the `--enable-introspection` option to the configure script. Generate the `Cvc-1.0.gir`, `CDesktopEnums-3.0.gir` and `CinnamonDesktop-3.0.gir` GIR metadata files to provide dynamic bindings for the languages other than C to the `libcinnamon-desktop` and the `libcvc` libraries.

This flag should be enabled if there is a need for GObject Introspection bindings for the libraries.

### systemd
Install the `cinnamon-desktop.systemd.gschema.override` override file into the `/usr/share/glib-2.0/schemas` directory to change default settings for GSettings database for better integration with the SystemD's logind session manager.

This flag should be enabled for a system that runs SystemD as its init system.
