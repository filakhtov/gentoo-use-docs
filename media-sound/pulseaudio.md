# media-sound/pulseaudio

### alsa
Pass the `--enable-alsa` option to the configure script. Build and install the `module-alsa-sink`, `module-alsa-source` and `module-alsa-card` PulseAudio plugins that allow to use the ALSA (Advance Linux Sound Architecture) subsystem to access sound hardware.

This flag should normally be enabled for standard desktop systems.

### alsa-plugin
Only works if the `alsa` flag is also enabled. Pull the [media-plugins/alsa-plugins](../media-plugins/alsa-plugins.md) package with the `pulseaudio` flag enabled as a dependency. Provide an ability for applications that use ALSA API to seamlessly use PulseAudio instead.

This flag is recommended for the regular desktop system.

### asyncns
Pass the `--enable-asyncns` option to the configure script. Use the `libasyncns` library for asynchronous name resolution when connecting to a network sink.

It is safe to disable the flag.

### bluetooth
Pass the `--enable-bluez5` and the `--disable-bluez4` options to the configure script. Build and install the `module-bluetooth-discover`, `module-bluetooth-policy`, `module-bluez5-discover` and the `module-bluez5-device` plugins to detect available bluetooth audio devices using BlueZ, handle Bluetooth policies and proximity volume control.

This flag should be enabled if there is a need to use Bluetooth audio devices.

### caps
Pass the `--with-caps` option to the configure script. Use the `libcap` library to drop root privileges and only preserve capabilities that are required for normal operation after the initialization. This is a security feature.

It is recommended to enable the flag.

### dbus
Pass the `--enable-dbus` option to the configure script. Build and install the `module-dbus-protocol` module to enable PulseAudio's D-Bus interface, the `module-console-kit` plugin to create a client for each ConsoleKit session of a user and the `module-rygel-media-server` - a UPnP MediaServer Plugin for Rygel to stream audio to the DLAN/UPnP compatible devices.

It is safe to disable the flag.

### doc
Use the Doxygen tool to generate an API documentation in an HTML format out of the source code and annotations and install it into the `/usr/share/doc/pulseaudio-<VERSION>` directory.

The flag can be safely disabled.

### equalizer
Pass the `--with-fftw` option to the configure script. Build and install the `module-equalizer-sink` that uses the Fastest Fourier Transform in the West library to provide a general purpose equalizer that can be applied over a sink.

It is safe to disable the flag.

### gconf
Pull in the [gnome-base/gconf](../gnome-base/gconf.md) package as a dependency to provide the `gsettings-data-convert` tool that is used for copying settings from the GConf configuration backend into the GSettings one. Note: this is one-shot operation and this flag can be disabled once migration is done.

This flag should only be enabled if there is a need to migrate PulseAudio settings from GConf.

### gdbm
Pass the `--with-database=gdbm` (instead of `simple`) option to the configure script. Use the GNU dbm library to store PulseAudio settings in the dbm format instead of simple binary data storage.

The flag can be safely disabled.

### glib
Pass the `--enable-glib2` and the `--enable-gsettings` options to the configure script. Build and install the `libpulse-mainloop-glib` for integration with the `libglib2` library to allow using PulseAudio client library for GLib-based programs. Also build `module-gsettings` plugin to store user's PulseAudio settings in the GSettings backend.

This flag is recommended for regular desktop systems.

### gtk
Pass the `--enable-gtk3` option to the configure script. Build a demo GTK+ test application.

This flag should be disabled.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable the IPv6 protocol support in the PulseAudio server to provide an ability to connect to and accept connections from IPv6 clients and servers.

This flag should be enabled if there is a need to use PulseAudio network functionality on the IPv6 enabled network.

### jack
Pass the `--enable-jack` option to the configure script. Build and install the `module-jack-sink` and `module-jack-source` (also `module-jackdbus-detect` if the `dbus` flag is also enabled) PulseAudio plugins that allow to use JACK (JACK Audio Connection Kit) subsystem for audio output.

This flag should only be enabled if there is a need for PulseAudio to coexist with JACK on the same system.

### libressl
Only work if the `ssl` flag is also enabled. Allow to use the `LibreSSL` cryptographic library instead of the `OpenSSL`. For details see the `ssl` flag.

This flag should only be toggled system-wide as these two libraries can not be installed at the same time.

### libsamplerate
Pass the `--enable-samplerate` option to the configure script. Use the `libsamplerate` library to perform resampling instead of the default speex method.

This flag should be disabled, because libsamplerate based resamplers are now deprecated in PulseAudio.

### lirc
Pass the `--enable-lirc` option to the configure script. Build and install the `module-lirc` plugin to provide an ability to adjust the volume of a sink when the volume buttons of an infrared remote control are pressed (through LIRC - Linux Infrared Remote Control).

It is safe to disable the flag.

### native-headset
This flag only works if the `bluetooth` flag is enabled. Pass the `--enable-bluez5-native-headset` option to the configure script. Provide support for `headset=native` parameter of the `module-bluetooth-discover` plugin to only enable HSP (Headset Profile) mode for devices that rely on SCO audio encoded in 64 kbit/s CVSD or PCM and a subset of AT commands from GSM 07.07 for minimal controls including the ability to ring, answer a call, hang up and adjust the volume.

This flag should be enabled if there is a need to use HSP bluetooth devices with PulseAudio.

### ofono-headset
This flag only works if the `bluetooth` flag is enabled. Pass the `--enable-bluez5-ofono-headset` option to the configure script. Provide support for `headset=ofono` parameter of the `module-bluetooth-discover` plugin to only enable HFP (Hands-Free Profile) mode that is mainly used in car hands-free kits to communicate with mobile phones in the car.

This flag should be enabled if there is a need to use HFP bluetooth devices with PulseAudio.

### orc
Pass the `--enable-orc` option to the configure script. Use the `liborc` library to execute CPU-agnostic SIMD code to improve CPU-intensive tasks, such as resampling.

It is recommended to enable this flag to improve performance.

### oss
Pass the `--enable-oss-output` option to the configure script. Build and install the `module-oss` PulseAudio plugin that can be used to access sound hardware via the OSS (Open Sound System).

This flag should normally be disabled as the OSS is deprecated.

### qt5
This flag is only works if the `equalizer` flag is enabled. Build and install the `qpaeq` - a graphical equalizer utility written in Qt.

It is safe to disable the flag.

### realtime
Pull in the [sys-auth/rtkit](../sys-auth/rtkit.md) package as a dependency. Use a RealtimeKit daemon to gain a real-time priority while running a PulseAudio server to avoid audio hiccups and delays. This will increase resource utilization by a PulseAudio server.

The flag should only be enabled if there is a need for real-time priority.

### selinux
Pull in the [sec-policy/selinux-pulseaudio](../sec-policy/selinux-pulseaudio.md) package as a dependency. Install SELinux policies to allow a PulseAudio daemon to properly run under a SELinux-restricted kernel.

This flag should only ever be toggle system-wide, i.e. as part of the SELinux-enabled portage profile.

### sox
Pass the `--with-soxr` option to the configure script. Use the `libsoxr` library to provide alternative resampling mechanisms. New resampling methods, the `soxr-mq`, `soxr-hq` and `soxr-vhq` can be accessed via the `resample-methods` configuration parameter.

This flag should be enabled if there is a need to resample sound before an output as it provides greater control and higher quality, however increases latency.

### ssl
Pass the `--enable-openssl` option to the configure script. Build and install the `module-raop-discover` and the `module-raop-sink` plugins to stream audio data to products that support the RAOP (Remote Audio Output Protocol) protocol to provide Wireless Network Sound (aka Apple Airtunes) including mDNS/DNS-SD Service Discovery of RAOP devices.

This flag should only be enabled if there is a need to use RAOP protocol.

### system-wide
Create the `pulse` user and the `pulse` and `pulse-access` groups. Install an `init.d` startup script and the SystemD service for the PulseAudio server. Enable the system mode for usage on thin client or embedded setups, where no real local user exists, where access is exclusively via the network, and where state data is flushed on each session termination.

This flag should normally be disabled.

### systemd
Pass the `--enable-systemd-daemon`, `--enable-systemd-login` and `--enable-systemd-journal` options to the configure script. Provide support for socket activation for PulseAudio server daemon under the SystemD init daemon and enable logging via the SystemD journal. Build and install the `module-systemd-login` PulseAudion plugin that creates a client for each login session of the user.

This flag should be enabled on the systems that use the SystemD init daemon.

### tcpd
Pass the `--enable-tcpwrap` option to the configure script. Enable support for the TCP wrappers (aka `tcpd`) tool to provide fine-grained control over network connections established to the PulseAudio server via an ACL system.

This flag should normally be disabled as TCP wrappers is obsolete and unmaintained.

### test
Pass the `--enable-default-build-tests` option to the configure script. Execute a `make check` command from the `src` subdirectory of the source tree. Build test utilities and a test suite provided with the source code and run it. This will extend the build time.

This flag should normally be disabled as these tests are mainly useful for developers, testers and the Gentoo team.

### udev
This flag only makes sense if the `alsa` or the `oss` flag is enabled. Pass the `--enable-udev` option to the configure script. Build and install the `module-udev-detect` PulseAudio plugin that allows to detect audio devices on the system using Udev.

This flag should normally be enabled on a regular desktop system.

### webrtc-aec
Pass the `--enable-webrtc-aec` option to the configure script. Use the WebRTC Audio Processing module to provide microphone echo cancellation functionality. This support will be built into the `module-echo-cancel` PulseAudio plugin and can be accessed via the `aec_method` configuration parameter.

This flag should be enabled if there are multiple microphone recorders on the target system that can be used for the echo cancellation.

### X
Pass the `--enable-x11` option to the configure script. Build and install the `module-x11-bell`, `module-x11-publish`, `module-x11-xsmp` and the `module-x11-cork-request` plugins that provide access credentials to the PulseAudio server for the X clients, intercept X11 bell events and plays a sound on each occurence, register to the X11 session manager and synthesize X11 media key events. Install the `start-pulseaudio-x11` script that is used to automatically start the PulseAudio server via the XDG (X Desktop Group) autostart and load aforementioned modules.

This flag should only be enabled if the target system runs the X Server.

### zeroconf
Pass the `--enable-avahi` option to the configure script. Build and install the `module-zeroconf-publish` plugin to publish all local sinks and sources using mDNS Zeroconf to provide network auto-discovery support for the PulseAudio server.

This flag should only be enabled if there is a need to use Zeroconf.
