# x11-libs/libva

### wayland
Pass the `-Dwith-wayland=true` option to the Meson build script. Build and install the `libva-wayland` library that provides an ability to render decoded and processed video frames onto a Wayland surface. Note: actual backend driver has to support the Wayland rendering too for this to work.

This flag should only be enabled on systems that use the Wayland display server.

### X
Pass the `-Dwith_x11=true` option to the meson build script. Build and install the `libva-x11` library that provide an ability to render decoded and processed video frames onto the (local) X server drawable areas. Note: actual backend driver has to support the X11 rendering too for this to work.

This flag should be enabled if the target system runs X window server.
