# sys-boot/plymouth

### debug
Pass the `--enable-tracing` option to the configure script. Produce an additional debug log output at runtime that contains function names and their location in the source code tree.

This flag should be disabled, unless there is a need to debug and trace the problem with Plymouth.

### drm
Pass the `--enable-drm` option to the configure script. Enable support for the DRM (Direct Rendering Managerand) and KMS (Kernel modesetting) drivers to allow rendering graphical boot animations. When disabled, Plymouth will fall back to a text mode.

The flag should be enabled if there is a need to display graphical boot animations.

### gtk
Pass the `--enable-gtk` option to the configure script. Enable the GTK renderer that allows executing plymouth inside a running X11 window session without booting the system.

This flag can be safely disabled.

### pango
Pass the `--enable-pango` option to the configure script. Enable support for displaying passphrase prompts, e.g. when asking a user to enther the key for an encrypted device.

This flag can be safely disabled if there is no need to ask passphrases during an early boot.

### split-usr
When enabled, install Plymouth binaries and libraries into the `/usr/bin` and `/usr/sbin` directories, otherwise install everything in `/bin` and `/sbin` and create compatibility symlinks inside of the `/usr` subtree.

This flag can be safely disabled if the system does not use a separate partition for the `/usr` directory.

### static-libs
Pass the `--enable-static` and `--disable-shared` options to the configure script (or vice versa when the flag is disabled). Build and install only a static version of the plymouth libraries.

This flag should only ever be enabled if there is an explicit need for the static libraries.

### udev
Pass the `--with-udev` option to the configure script. Integrate with Udev device manager in order to enumerate and discover available DRM devices to show animation on.

It is recommended to enable this flag.
