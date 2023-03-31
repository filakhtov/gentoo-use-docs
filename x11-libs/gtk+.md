# x11-libs/gtk+

### aqua
Pass the `-Dquartz_backend=true` option to the meson build script. Enable support for the Quartz backend of the GDK (GIMP Drawing Kit) library. This backend is only provided by the macOS and has no use for the Gentoo Linux system.

This flag should be disabled.

### broadway
Pass the `-Dbroadway_backend=true` option to the meson build script. Enable support for the Broadway backend of the GDK (GIMP Drawing Kit) library. This backend provides an ability to render GTK+ interfaces using an HTML5 format and allow using GTK+ based applications directly in a web browser.

It is safe to disable the flag.

### cloudproviders
Pass the `-Dcloudproviders=true` option to the meson build script. Use the `libcloudproviders` library to enable support for various cloud storage providers, like NextCloud, and expose them as a place in navigation sidebar.

This flag can be safely disabled.

### colord
Pass the `-Dcolord=yes` option to the meson build script. Enable a GTK+ support for the `colord` daemon to provide color management abilities. Allow to change and apply new profiles to the display. Provide an ability to associate color profiles with various devices such as monitors, printers or scanners and allow to calibrate these devices if they have necessary hadware or software suport.

It is safe to disable the flag, however GTK+ color management abilities will be lost.

### cups
Append the `cups` option to the `-Dprint_backends=` option and pass it to the meson build script. Build and install the `CUPS` (Common UNIX Printing System) printing backend. Provide an ability for the GTK based applications to print using local and remote printers via a raw socket, LPD, IPP or SMB protocol depending on printer capabilities and `CUPS` daemon settings. Handle authentication if necessary.

This flag should be enabled if there is a need to support the `CUPS` based printing.

### examples
Pass the `-Ddemos=true` and `-Dexamples=true` to the meson build script. Build and install the `gtk3-demo`, `gtk3-demo-application` and `gtk3-widget-factory` demo programs. Install the C example source code to show various usages of the GTK+ toolkit into the `/usr/share/doc/gtk+-<VERSION>/examples` directory.

It is safe to disable the flag.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Generate documentation using the GTK-Doc tool in the HTML format and install it into the `/usr/share/gtk-doc/html/gtk<VERSION>/` directory, including widgets and objects description and usage, core reference, theming and so on.

This flag can be safely disabled.

### introspection
Pass the `-Dintrospection=true` option to the meson build script. Generate GIR metadata `Gdk-3.0.gir`, `Gtk-3.0.gir` (and also `GdkX11-3.0.gir` if the `X` flag is enabled) files during a build time and generate typelib from them to provide dynamic bindings support for languages other than C.

It is safe to disable the flag.

### sysprof
Pass the `-Dprofiler=true` option to the meson build script. Enable profiling support and provide an ability to generate syscap files, by passing the `GTK_TRACE=1` environment variable to any GTK-based application, that subsequently can be loaded into the sysprof for analysis.

This flag should normally be disabled.

### test
Pass the `-Dtests=true` option to the meson build script. Build the test suite provide with the source code. Execute the `meson script` to run tests after the main build is completed and check for any regressions. This will extend the build time.

The flag should normally be disabled as test suite is primarily useful for the maintainers, testers and developers.

### vim-syntax
Pull in the [app-vim/gtk-syntax](../app-vim/gtk-syntax.md) package as a dependency. Extend standard C syntax highlighting to provide additional types, functions, macros, and constants to support syntax highlight for `xlib`, `glib` (including `gobject` and `gio`), `gdk-pixbuf`, `gtk2` and `gdk2`, `gtk3` and `gdk3`, `atk`, `at-spi2`, `cairo`, `clutter`, `dbus-glib`, `evince`, `fftw3`, `gimp`, `gnome-desktop`, `gstreamer`, `gtkglext`, `gtksourceview`, `gudev`, `gusb`, `json-glib`, `libglade`, `libgsf`, `libnotify`, `librsvg`, `libunique`, `libwnck`, `pango`, `poppler` and `vte` source files.

It is safe to disable this flag.

### wayland
Pass the `-Dwayland_backend=true` option to the meson build script. Enable support for the Wayland backend of the GDK (GIMP Drawing Kit) library. Provide an ability to run GTK+ based applications under the Wayland display server.

This flag should only be enabled if the target system runs a Desktop Environment on top of the Wayland. This feature is highly experimental.

### X
Pass the `-x11_backend=true` option to the meson build script. Build and install X11 backend for the GDK (GIMP Drawing Kit) library. Provide an ability to run GTK+ application under the X Window System. Use the XComposite and XDamage extensions to provide offscreen rendering and composition abilities. Use Xrandr extension to control size, orientation and reflection for a screen.

This flag should be enabled if there is a need to run desktop environment on top of X server.

### xinerama
Requires the `X` flag to be enabled. Pass the `-Dxinerama=yes` option to the meson build script. Use the Xinerama API to query multi-monitor geometry and provide proper window positioning and sizing for screens that are configured using the Xinerama X extension.

This flag should normally be disabled. Xinerama is an outdated way of doing multi-monitor setup and is nowadays replaced by the Xrandr extension.
