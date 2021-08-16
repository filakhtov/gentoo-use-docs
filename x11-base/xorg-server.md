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
This flag is incompatible with the `systemd` flag. Pull in the [sys-auth/elogind](../sys-auth/elogind.md) and other relevant packages as dependencies and pass the `--enable-systemd-logind` and `--disable-install-setuid` options to the configure script. Enable integration with the elogind daemon to provide an ability to run Xorg from an unprivileged user and provide necessary access to various devices.

This flag should be normally disabled, unless there is a need to use elogind with Xorg, for example when running the GNOME desktop environment without SystemD.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable support for the IPv6 protocol in the Xorg networking code, e.g. for the XDMCP (X Display Manager Control Protocol).

This flag should be enabled if there is a need to use an X Server remote functionality over an IPv6-capable network.

### kdrive
Pass the `--enable-kdrive`, `--enable-kdrive-kbd`, `--enable-kdrive-mouse` and the `--enable-kdrive-evdev` options to the configure script. Build and install a KDrive X server (aka Tiny X, TinyX) that is designed for low memory environments that tends to avoid large memory allocations at runtime, and tries to perform operations "on the fly" whenever possible. It is completely self-contained: it does not require any configuration files or on-disk fonts and all configuration is done at compile time and through command-line flags.

This flag should only be enabled if the KDrive X server is necessary.

### minimal
Pass the `--disable-record`, `--disable-xfree86-utils`, `--disable-dri`, `--disable-dri2`, `--disable-dri3`, `--disable-glamor` and the `--disable-glx` options to the configure script. Build a minimal version of the X server without the Record, DRI (Direct Rendering Infrastructure), DRI2, DRI3, Glamor and GLX (OpenGL Extension to the X Window System) extensions. Also, do not build the `gtf` tool to calculate VESA GTF mode lines and the `cvt` tool to calculate VESA CVT mode lines. Note, that Wayland without Glamor will not have a hardware acceleration support and may cause unacceptable performance issues.

This flag should normally be disabled, unless there is an explicit need for the very minimal X server build.

### selinux
Pull in the [sec-policy/selinux-xserver](../sec-policy/selinux-xserver.md) package as a dependency to install SELinux policies that are necessary for X server to propely run under a SELinux-restricted kernel.

This flag should only ever be toggled system wide, i.e. as part of the SELinux-enabled Portage profile.

### static-libs
Remove a `-Wl,-Bdirect` option from a `CFLAGS`, `CPPFLAGS`, `CXXFLAGS`, `CCASFLAGS`, `FFLAGS`, `FCFLAGS` and an `LDFLAGS` variables and a `-Bdirect` option from a `LDFLAGS` variable for a duration of a build. Build and install statically linked libraries, e.g. a `...` and so forth.

This flag should normally be disabled, unless there is an explicit need for static libraries.

### suid
Pass the `--enable-install-setuid` option to the configure script if the `systemd` and `elogind` flags are disabled, and if one of them is enabled then pass the `--enable-suid-wrapper` instead. The former option will set the `suid` bit on the `/usr/bin/Xorg` binary so that it is executed with root privileges even by the unprivileged users. The latter, will install a wrapper with `suid` bit set that will launch actual processes with root privileges if the system does not supports KMS or KMS drivers are not properly loaded, otherwise it will drop privileges and start an unprivileged `Xorg` process.

This flag should normally be disabled, to increase security and remove unnecessary privileges, unless on the non-KMS compatible system.

### systemd
Pass the `--with-systemd-daemon`, `--disable-install-setuid` and the `--enable-systemd-logind` options to the configure script. Integrate with the SystemD's logind daemon to provide an ability to be run from within a systemd user service as an unprivileged X server, delegating device management to logind, and also can be made into a socket activated service.

This flag should be enabled if there is a desire to run X server from within the user session.

### test
Pass the `--enable-unit-tests` option to the configure script. Build a test suite provided with the source code and run it after the main build is completed to check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily useful for the maintainers, developers and testers.

### udev
Pass the `--enable-config-udev` option to the configure script. Build and install the Udev backend to handle hotplugged input devices. Upon startup the X server queries this backend for the list of input devices and initializes them accordingly and when a new device is added at runtime, the server is notified and adds it at runtime.

It is recommended to enable this flag on a usual desktop system, to provide hotplug device support.

### unwind
Pass the `--enable-libunwind` option to the configure script. Use the `libunwind` library to generate backtraces for debugging messages more reliably than glibc's `backtrace`.

This flag can be enabled to assist in debuggin X server code.

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
