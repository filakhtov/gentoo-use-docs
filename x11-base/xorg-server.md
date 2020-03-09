# x11-base/xorg-server

### debug
Pass the `--enable-debug` option to the configure script. Enable printing of additional debugging messages at runtime.

This flag should only be enabled for debuggin purposes.

### dmx
Pass the `--enable-dmx` option to the configure script. Build the DMX (Distributed Multihead X) server - a proxy X server that provides multi-head support for multiple displays attached to different machines (each of which is running a typical X server). When Xinerama is used with Xdmx, the multiple displays on multiple machines are presented to the user as a single unified screen.

This flag should only be enabled if there is a need to proxy X server from different machines.

### doc
Pass the `--with-doxygen` and the `--with-xmlto` options to the configure script. Generate additional documentation using the DocBook and xmlto tools and install it into the `/usr/share/doc/xorg-server-<VERSION>` directory.

It is safe to disable the flag.

### elogind
This flag is incompatible with the `systemd` flag. Pull in the [sys-auth/elogind](../sys-auth/elogind.md) and other relevant packages as dependencies and pass the `--enable-systemd-logind` option to the configure flag. Enable integration with the elogind daemon to provide an ability to run Xorg from an unprivileged user and provide necessary access to various devices.

This flag should be normally disabled, unless there is a need to use elogind with Xorg, for example when running the GNOME desktop environment without SystemD.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable support for the IPv6 protocol in the Xorg networking code, e.g. for the XDMCP (X Display Manager Control Protocol).

This flag should be enabled if there is a need to use an X Server remote functionality over an IPv6-capable network.

### kdrive
Pass the `--enable-kdrive`, `--enable-kdrive-kbd`, `--enable-kdrive-mouse` and the `--enable-kdrive-evdev` options to the configure script. Build and install a KDrive X server (aka Tiny X, TinyX) that is designed for low memory environments that tends to avoid large memory allocations at runtime, and tries to perform operations "on the fly" whenever possible. It is completely self-contained: it does not require any configuration files or on-disk fonts and all configuration is done at compile time and through command-line flags.

This flag should only be enabled if the KDrive X server is necessary.

### libglvnd
Pull in necessary dependencies and ensure their flags are properly configured for X11 to support `libglvnd` and allow rendering using multiple GPUs from different vendors across separate X screens.

This flag can be safely disabled and should only be enabled on a system with multiple GPUs from different vendors, such as laptop hybrid graphics.

### libressl
Use the LibreSSL library instead of the OpenSSL library.

This flag should only ever be toggled system-wide, because two libraries cant be installed at the same time.

### minimal
Pass the `--disable-record`, `--disable-xfree86-utils`, `--disable-dri`, `--disable-dri2` and the `--disable-glx` options to the configure script. Build a minimal version of the X server without the Record, DRI (Direct Rendering Infrastructure), DRI2 and GLX (OpenGL Extension to the X Window System) extensions. Also, do not build the `gtf` tool to calculate VESA GTF mode lines and the `cvt` tool to calculate VESA CVT mode lines.

This flag should normally be disabled, unless there is an explicit need for the very minimal X server build.

### selinux
Pull in the [sec-policy/selinux-xserver](../sec-policy/selinux-xserver.md) package as a dependency to install SELinux policies that are necessary for X server to propely run under a SELinux-restricted kernel.

This flag should only ever be toggled system wide, i.e. as part of the SELinux-enabled Portage profile.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install statically linked libraries, e.g. a `...` and so forth.

This flag should normally be disabled, unless there is an explicit need for static libraries.

### suid
Pass the `--enable-install-setuid` option to the configure script. Set the `suid` bit on the `/usr/bin/Xorg` binary so that it is executed as root. Disabling this flag will increase security by allowing X server to run from an unprivileged user, however requires additional special workarounds, as none of login managers are currently capable of doing necessary permission handling. See [Gentoo Wiki](https://wiki.gentoo.org/wiki/Non_root_Xorg) for details.

This flag should normally be disabled, however can be enabled if increased security is a priority.

### systemd
Pass the `--with-systemd-daemon` and the `--enable-systemd-logind` options to the configure script. Integrate with the SystemD's logind daemon to provide an ability to be run from within a systemd user service as an unprivileged X server, delegating device management to logind, and also can be made into a socket activated service.

This flag should be enabled if there is a desire to run X server from within the user session.

### tslib
The flag only makes sense if the `kdrive` flag is also enabled. Pass the `--enable-tslib` option to the configure script. Build and install the touchscreen driver for the KDrive server that uses `tslib` library to provide an access to touch-enabled input devices. Note, that servers flavors other than KDrive should use the [x11-drivers/xf86-input-tslib](../x11-drivers/xf86-input-tslib.md) package instead.

This flag should only be enabled if there is a need to use touchscreen devices with the KDrive X server.

### udev
Pass the `--enable-config-udev` option to the configure script. Build and install the Udev backend to handle hotplugged input devices. Upon startup the X server queries this backend for the list of input devices and initializes them accordingly and when a new device is added at runtime, the server is notified and adds it at runtime.

It is recommended to enable this flag on a usual desktop system, to provide hotplug device support.

### unwind
Pass the `--enable-libunwind` option to the configure script. Use the `libunwind` library to generate backtraces for debugging messages more reliably than glibc's `backtrace`.

This flag can be enabled to assist in debuggin X server code.

### wayland
Pass the `--enable-xwayland` option to the configure script. Build a modified version of the Xorg server to use Wayland input devices for input and forward either the root window or individual top-level windows as Wayland surfaces. The server still runs the same 2D driver with the same acceleration code as it does when it runs natively, but Wayland handles presentation of the windows instead of KMS.

This flag should be enabled if there is a need to run Wayland window system with X based applications.

### xcsecurity
Pass the `--enable-xcsecurity` option to the configure script. Build the X Security Extension to allow distinguishing between trusted clients - that are permitted to use the entire X protocol, and untrusted clients - that are limited in what they do, e.g. they are prohibited from accessing window images of trusted clients. Enable support for runtime `-sp` option to specify a file that contains security policies.

This flag should normally be disabled, unless there is a need for the X Security extension.

### xephyr
Pass the `--enable-xephyr` option to the configure script. Build and install a Xephyr flavour of the X server - a display server software implementing the X11 display server protocol based on KDrive which targets a window on a host X Server as its framebuffer. Unlike the similar Xnest, Xephyr supports modern X extensions such as composite, damage, randr, etc, and uses SHM images and shadow framebuffer updates to provide good performance.

This flag should normally be disabled, unless there is a need to perform "X nesting", including access to a remote X server.

### xnest
Pass the `--enable-xnest` option to the configure script. Build and install an Xnest server - which is both an X client and an X server. Xnest is a client of the real server which manages windows and graphics requests on Xnest's behalf, and is a server to its own clients - it manages windows and graphics requests and appears to be a conventional server for them.

This flag should be disabled, and if nesting functionality is needed, then Xephyr would be a better choice.

### xorg
Pass the `--enable-xorg` option to the configure script. Build and install Xorg server - a full featured X Window system implementation that was originally designed for *NIX operating systems running on Intel x86 hardware, but runs on a wider range of hardware and OS platforms nowadays. This server is created by the X.Org Foundation from the XFree86 Project's XFree86 4.4rc2 release. This is the most commonly used X Server implementation.

This flag should normally be enabled for the desktop system, unless there are specific needs, like running Wayland.

### xvfb
Pass the `--enable-xvfb` option to the configure script. Build and install the Xvfb (X virtual framebuffer) - a display server implementing the X11 display server protocol, but in contrast to other display servers, Xvfb performs all graphical operations in virtual memory without showing any screen output.

This flag should normally be disabled as Xvfb is primarily used for testing.
