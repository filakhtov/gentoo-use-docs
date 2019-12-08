# gnome-base/gsettings-desktop-schemas

### introspection
Pass the `-Dintrospection=true` (`false` if the flag is disabled) option to the meson build script. Generate GIR metadata `GDesktopEnums-3.0.gir` file and generate a typelib from it during a build time to provide dynamic bindings support for languages other than C.

This flag can be safely disabled.
