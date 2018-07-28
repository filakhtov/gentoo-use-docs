# x11-libs/gtk+

### aqua
Pass the `--enable-quartz-backend` option to the configure script. Enable support for the Quartz backend of the GDK (GIMP Drawing Kit) library. This backend is only provided by the macOS and has no use for the Gentoo Linux system.

This flag should be disabled.

### broadway
Pass the `--enable-broadway-backend` option to the configure script. Enable support for the Broadway backend of the GDK (GIMP Drawing Kit) library. This backend provides an ability to render GTK+ interfaces using an HTML5 format and allow using GTK+ based applications directly in a web browser.

It is safe to disable the flag.

### cloudprint
Pass the `--enable-cloudprint` option to the configure script. Enable Google Cloud Print support for the GTK+ toolkit. Provide a native support for printing using cloud-shared printers and an ability to save to Google Drive from printing dialog.

This flag can be safely disabled.

### colord
Pass the `--enable-colord` option to the configure script. Enable a GTK+ support for the `colord` daemon to provide color management abilities. Allow to change and apply new profiles to the display. Provide an ability to associate color profiles with various devices such as monitors, printers or scanners and allow to calibrate these devices if they have necessary hadware or software suport.

It is safe to disable the flag, however GTK+ color management abilities will be lost.

### cups
Pass the `--enable-cups=auto` option to the configure script. Build and install the `CUPS` (Common UNIX Printing System) printing backend. Provide an ability for the GTK based applications to print using local and remote printers via a raw socket, LPD, IPP or SMB protocol depending on printer capabilities and `CUPS` daemon settings. Handle authentication if necessary.

This flag should be enabled if there is a need to support the `CUPS` based printing.

### examples
Examples and demo code are built by default, so this flag does nothing if enabled. When disabled, remove `Makefile` files from the `examples` and `demos` directories to avoid building them and thus speed up a build time. Build and install the `gtk3-demo`, `gtk3-demo-application` and `gtk3-widget-factory` demo programs. Install the C example source code to show various usages of the GTK+ toolkit into the `/usr/share/doc/gtk+-<VERSION>/examples` directory.

It is safe to disable the flag.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate GIR metadata `Gdk-3.0.gir`, `Gtk-3.0.gir` (and also `GdkX11-3.0.gir` if the `X` flag is enabled) files during a build time and generate typelib from them to provide dynamic bindings support for languages other than C.

This flag can be safely disabled.

### test
Test code is built by default so disabling this flag removes `Makefile` files from the `testsuite` directory to avoid building unused code and speed-up a build. Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run a test suite provided with the source code. This will extend a build time.

The flag should normally be disabled as test suite is primarily useful for the Gentoo team, testers and developers.

### vim-syntax
Pull in the [app-vim/gtk-syntax](../app-vim/gtk-syntax.md) package as a dependency. Extend standard C syntax highlighting to provide additional types, functions, macros, and constants to support syntax highlight for `xlib`, `glib` (including `gobject` and `gio`), `gdk-pixbuf`, `gtk2` and `gdk2`, `gtk3` and `gdk3`, `atk`, `at-spi2`, `cairo`, `clutter`, `dbus-glib`, `evince`, `fftw3`, `gimp`, `gnome-desktop`, `gstreamer`, `gtkglext`, `gtksourceview`, `gudev`, `gusb`, `json-glib`, `libglade`, `libgsf`, `libnotify`, `librsvg`, `libunique`, `libwnck`, `pango`, `poppler` and `vte` source files.

It is safe to disable this flag.

### wayland
Pass the `--enable-wayland-backend` option to the configure script. Enable support for the Wayland backend of the GDK (GIMP Drawing Kit) library. Provide an ability to run GTK+ based applications under the Wayland display server.

This flag should only be enabled if the target system runs a Desktop Environment on top of the Wayland. This feature is highly experimental.

### X
Pass the `--enable-x11-backend`, `--enable-xcomposite`, `--enable-xdamage`, `--enable-xfixes`, `--enable-xkb`, and `--enable-xrandr` options to the configure script. Build and install X11 backend for the GDK (GIMP Drawing Kit) library. Provide an ability to run GTK+ application under the X Window System. Use the XComposite and XDamage extensions to provide offscreen rendering and composition abilities. Use Xrandr extension to control size, orientation and reflection for a screen.

This flag should be enabled if there is a need to run desktop environment on top of X server.

### xinerama
This flag does nothing if the `X` flag is disabled. Pass the `--enable-xinerama` option to the configure script. Use the Xinerama API to query multi-monitor geometry and provide proper window positioning and sizing for screens that are configured using the Xinerama X extension.

This flag should normally be disabled. Xinerama is an outdated way of doing multi-monitor setup and is nowadays replaced by the Xrandr extension.
