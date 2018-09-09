# media-libs/clutter

### aqua
Pass a `--enable-quartz-backend` option to a configure script. Integrate between the GLib main loop and the native system of the Core Foundation run loop and Cocoa event handling. Provide an ability to use the Quartz backend for rendering scenes on top of native macOS GUI and to load images into textures using the CoreGraphics framework.

This flag should be enabled on macOS systems.

### debug
Pass a `--enable-debug=yes` option to a configure script (`--enable-debug=minimum` when disabled). Build libraries with debugging symbols. Produce additional debugging messages at runtime.

This flag should only be enabled for debugging purposes.

### doc
Pass a `--enable-docs` option to a configure script. Generate and install additional documentation (cookbook) in an HTML format and install it into the `/usr/share/doc/clutter-<VERSION>` directory.

It is safe to disable the flag.

### egl
Pass a `--enable-egl-backend` and a `--enable-evdev-input` options to a configure script. Enable an `evdev` input device backend for reading the generic input events generated in the Linux kernel. Integrate with EGL (Khronos Native Platform Graphics Interface) API to provide an ability to render scenes within EGL windows.

This flag should be enabled if there is a need to run Clutter on top of a Wayland window server or directly on top of a framebuffer.

### gtk
Pass a `--enable-gdk-backend` option to a configure script. Enable a GDK backend that provides some specific API, allowing integration with the GDK (GIMP Drawing Kit) API for manipulating the stage window and handling events outside of Clutter. Provides better integration with Gtk+ applications if compared to an X11 backend.

This flag should be enabled for systems that use GNOME or Gtk+ based desktop environments.

### introspection
Pass a `--enable-instrospection` to a configure script. Generate and install a `Cally-1.0.gir` and a `Clutter-1.0.gir` (also `ClutterGdk-1.0.gir` if the `gtk` flag is enabled and `ClutterX11-1.0.gir` if the `X` flag is enabled) GIR metadata files to provide dynamic bindings for the `libclutter` family of libraries to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### test
Pass a `--enable-gdk-pixbuf` option to a configure script. Start a new Xvfb session and execute the `make check` command from the `tests/conform` subdirectory inside of it when the main build is completed. Run a test suite provided with the source code. This will extend a build time.

The flag should normally be disabled. It is mainly targeted for the Gentoo team, testers and developers.

### wayland
Pass a `--enable-wayland-backend` and a `--enable-wayland-compositor` options to a configure script. Enable a Wayland specific backend. Provide an ability to properly handle device input events received through Wayland and enable Wayland specific APIs to aid in writing Clutter based compositors.

This flag should be enabled if the target system need to run Clutter on top of the Wayland display server.

### X
Pass a `--enable-xinput` and a `--enable-x11-backend` options to a configure script. Enable the X11 backend that provides some specific API, allowing integration with the Xlibs API for embedding and manipulating the stage window, or for trapping X errors. Enables the use of the XInput extension (if present) on connected X Server to allow for multiple pointing devices to be used.

This flag should be enabled if there is a need to run Clutter on top of X Server where GDK backend is not appropriate.
