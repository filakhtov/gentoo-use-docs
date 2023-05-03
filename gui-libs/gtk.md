# gui-libs/gtk

### aqua
Pass the `-Dmacos-backend=true` option to the Meson build script. Enable support for the Quartz backend of the GDK (GIMP Drawing Kit) library. This backend is only provided by the macOS and has no use for the Gentoo Linux system.

This flag should be disabled on Linux systems.

### broadway
Pass the `-Dbroadway-backend=true` option to the Meson build script. Enable support for the Broadway backend of the GDK (GIMP Drawing Kit) library. This backend provides an ability to render GTK+ interfaces using an HTML5 format and allow using GTK+ based applications directly in a web browser.

It is safe to disable the flag.

### cloudproviders
Pass the `-Dcloudproviders=enabled` option to the Meson build script. This flag controls whether GTK should use the `libcloudproviders` library for supporting various Cloud storage APIs in the file chooser.

This flag can be safely disabled.

### colord
Pass the `-Dcolord=enabled` option to the Meson build script. Enable support for the `colord` daemon to provide color management abilities in the GTK apps. Allow to change and apply new profiles to the display. Provide an ability to associate color profiles with various devices such as monitors, printers or scanners and allow to calibrate these devices if they have necessary hadware or software suport.

It is safe to disable the flag, however GTK color management abilities will be lost.

### cups
Pass the `-Dprint-cups=enabled` option to the Meson build script. Build and install the `CUPS` (Common UNIX Printing System) printing backend. Provide an ability for the GTK-based applications to print using local and remote printers via a raw socket, LPD, IPP or SMB protocol depending on printer capabilities and `CUPS` daemon settings. Handle authentication if necessary.

This flag should be enabled if there is a need to support the `CUPS` based printing.

### examples
Pass the `-Dbuild-examples=true` and `-Ddemos=true` options to the Meson build script. Build and install examples and demo code, including the `gtk4-demo`, `gtk4-demo-application`, `gtk4-icon-browser`, `gtk4-constraint-editor`, `gtk4-node-editor`, `gtk4-print-editor` and `gtk4-widget-factory` demo programs. Install the C example source code to show various usages of the GTK+ toolkit into the `/usr/share/doc/gtk+-<VERSION>/examples` directory.

This flag should normally be disabled.

### ffmpeg
Pass the `-Dmedia-ffmpeg=enabled` option to the Meson build script. Build the experimental FFmpeg media backend that allows playing video files through `GtkMediaFile` API using the FFmpeg media library.

This is an experimental backend and should be used with care.

### gstreamer
Pass the `-Dmedia-gstreamer=enabled` option to the Meson build script. Build the GStreamer media backend that allows playing video files through the `GtkMediaFile` API using the GStreamer media framework.

It is safe to disable this flag, however `GtkMediaFile` API will be unavailable.

### introspection
Pass the `-Dintrospection=enabled` option to the Meson build script. Generate the `Gdk-4.0.gir`, `Gtk-4.0.gir`, `Gsk-4.0.gir` (also the `GdkX11-4.0.gir` if the `X` flag is enabled and `GdkWayland-4.0.gir` if the `wayland` flag is enabled) GIR metadata files to provide dynamic bindings for the `libgtk-4` library to languages other than C using the GObject Introspection infrastructure.

This flag can be safely disabled.

### sysprof
Pass the `-Dsysprof=enabled` option to the Meson build script. Enable profiling support and provide an ability to generate syscap files, by passing the `GTK_TRACE=1` environment variable to any GTK-based application, that subsequently can be loaded into the sysprof for analysis.

This flag should normally be disabled.

### test
Pass the `-Dbuild-testsuite=true` option to the Meson build script. Build the test suites provided with the source code and run it after the main build is completed to check for any regressions. When the `X` flag is enabled, start the virtual Xvfb session and execute the `meson test --setup=x11` command. When the `wayland` flag is enabled execute the `meson test --setup=wayland` command inside of the headless Weston compositor. This will extend the build time.

This flag should normally be disabled because these tests are primarily oriented towards the developers, maintainers and testers.

### vulkan
Pass the `-Dvulkan=enabled` option to the Meson build script. Enable support for the experimental Vulkan graphics API, in addition to OpenGL and Cairo.

This feature is experimental and should be used with care.

### wayland
Pass the `-Dwayland-backend=true` option to the Meson build script. Enable support for the Wayland backend of the GDK (GIMP Drawing Kit) library. Provide an ability to run GTK+ based applications under the Wayland display server.

This flag should only be enabled if the target system runs a Desktop Environment on top of the Wayland. This feature is highly experimental.

### X
Pass the `-Dx11-backend=true` option to the Meson build script. Build and install X11 backend for the GDK (GIMP Drawing Kit) library. Provide an ability to run GTK+ application under the X Window System. Use the XComposite and XDamage extensions to provide offscreen rendering and composition abilities. Use Xrandr extension to control size, orientation and reflection for a screen.

This flag should be enabled if there is a need to run desktop environment on top of X server.
