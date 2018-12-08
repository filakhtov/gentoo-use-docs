# x11-libs/libva-intel-driver

### drm
Ensure that the `drm` flag is enabled for the [x11-libs/libva](../x11-libs/libva.md) package. Pass the `--enable-drm` option to the configure script. Enable renderless video frames processing on top of the DRM buffer.

See the `drm` flag of the [x11-libs/libva](../x11-libs/libva.md) package for more information, including when to enable this flag.

### wayland
Ensure that the `wayland` flag is enabled for the [x11-libs/libva](../x11-libs/libva.md) package. Pass the `--enable-wayland` option to the configure script. Provide an ability to render video frames directly to Wayland surfaces.

See the `wayland` flag of the [x11-libs/libva](../x11-libs/libva.md) package for more information, including when to enable this flag.

### X
Ensure that the `X` flag is enabled for the [x11-libs/libva](../x11-libs/libva.md) package. Pass the `--enable-x11` option to the configure script. Provide an ability to render frames directly to the X server drawable areas.

See the `X` flag of the [x11-libs/libva](../x11-libs/libva.md) package for more information, including when to enable this flag.
