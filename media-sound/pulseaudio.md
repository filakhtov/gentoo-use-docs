# media-sound/pulseaudio

### alsa
Pass the `-Dalsa=enabled` option to the meson build script. Build and install the `module-alsa-sink`, `module-alsa-source` and `module-alsa-card` PulseAudio plugins that allow to use the ALSA (Advance Linux Sound Architecture) subsystem to access sound hardware.

This flag should normally be enabled for standard desktop systems.

### alsa-plugin
Only works if the `alsa` flag is also enabled. Pull the [media-plugins/alsa-plugins](../media-plugins/alsa-plugins.md) package with the `pulseaudio` flag enabled as a dependency. Provide an ability for applications that use ALSA API to seamlessly use PulseAudio instead.

This flag is recommended for the regular desktop system.

### asyncns
Pass the `-Dasyncns=enabled` option to the meson build script. Use the `libasyncns` library for asynchronous name resolution when connecting to a network sink.

It is safe to disable the flag.

### bluetooth
Pass the `-Dbluez5=enabled` option to the meson build script. Build and install the `module-bluetooth-discover`, `module-bluetooth-policy`, `module-bluez5-discover` and the `module-bluez5-device` plugins to detect available bluetooth audio devices using BlueZ, handle Bluetooth policies and proximity volume control.

This flag should be enabled if there is a need to use Bluetooth audio devices.

### daemon
Pass the `-Ddaemon=true` option to the meson build script. Build and install the daemon binary that can be used to run Pulseaudio server in system-wide (see the `system-wide` flag) or per-user configuration.

This flag should be enabled, otherwise it would be impossible to run Pulseaudio sound server.

### dbus
Pass the `-Ddbus=enabled` option to the meson build script. Build and install the `module-dbus-protocol` module to enable PulseAudio's D-Bus interface, the `module-console-kit` plugin to create a client for each ConsoleKit session of a user and the `module-rygel-media-server` - a UPnP MediaServer Plugin for Rygel to stream audio to the DLAN/UPnP compatible devices.

It is safe to disable the flag.

### doc
Pass the `-Ddoxygen=true` option to the meson build script. Use the Doxygen tool to generate an API documentation in an HTML format out of the source code and annotations and install it into the `/usr/share/doc/pulseaudio-<VERSION>` directory.

The flag can be safely disabled.

### elogind
Pass the `-Delogind=enabled` option to the meson build script. Use the elogind for building the `module-systemd-login` PulseAudion plugin. See the `systemd` flag for details.

This flag should only be enabled on systems that use elogind.

### equalizer
Pass the `-Dfftw=enabled` option to the meson build script. Build and install the `module-equalizer-sink` that uses the Fastest Fourier Transform in the West library to provide a general purpose equalizer that can be applied over a sink.

It is safe to disable the flag.

### gdbm
Pass the `-Ddatabase=gdbm` (instead of `simple`) option to the meson build script. Use the GNU dbm library to store PulseAudio settings in the dbm format instead of simple binary data storage.

The flag can be safely disabled.

### glib
Pass the `-Dglib=enabled` and the `--Dgsettings=enabled` options to the meson build script. Build and install the `libpulse-mainloop-glib` for integration with the `libglib2` library to allow using PulseAudio client library for GLib-based programs. Also build `module-gsettings` plugin to store user's PulseAudio settings in the GSettings backend.

This flag is recommended for regular desktop systems.

### gstreamer
Pass the `-Dgstreamer=enabled` option to the meson build script. Use GStream-based RTP implementation, instead of PulseAudio-provided one to enable support for more advanced features like RTCP, non-PCM audio, and opening up the door to synchronized playback.

This flag should only be enabled if there is a need to use RTP with PulseAudio.

### gtk
Pass the `-Dgtk=enabled` option to the meson build script. Build a demo GTK+ test application.

This flag should be disabled.

### ipv6
Pass the `-Dipv6=true` option to the meson build script. Enable the IPv6 protocol support in the PulseAudio server to provide an ability to connect to and accept connections from IPv6 clients and servers.

This flag should be enabled if there is a need to use PulseAudio network functionality on the IPv6 enabled network.

### jack
Pass the `-Djack=enabled` option to the meson build script. Build and install the `module-jack-sink` and `module-jack-source` (also `module-jackdbus-detect` if the `dbus` flag is also enabled) PulseAudio plugins that allow to use JACK (JACK Audio Connection Kit) subsystem for audio output.

This flag should only be enabled if there is a need for PulseAudio to coexist with JACK on the same system.

### lirc
Pass the `-Dlirc=enabled` option to the meson build script. Build and install the `module-lirc` plugin to provide an ability to adjust the volume of a sink when the volume buttons of an infrared remote control are pressed (through LIRC - Linux Infrared Remote Control).

It is safe to disable the flag.

### native-headset
This flag only works if the `bluetooth` flag is enabled. Pass the `-Dbluez5-native-headset=true` option to the meson build script. Provide support for `headset=native` parameter of the `module-bluetooth-discover` plugin to only enable HSP (Headset Profile) mode for devices that rely on SCO audio encoded in 64 kbit/s CVSD or PCM and a subset of AT commands from GSM 07.07 for minimal controls including the ability to ring, answer a call, hang up and adjust the volume.

This flag should be enabled if there is a need to use HSP bluetooth devices with PulseAudio.

### ofono-headset
This flag only works if the `bluetooth` flag is enabled. Pass the `-Dnable-bluez5-ofono-headset=true` option to the meson build script. Provide support for `headset=ofono` parameter of the `module-bluetooth-discover` plugin to only enable HFP (Hands-Free Profile) mode that is mainly used in car hands-free kits to communicate with mobile phones in the car.

This flag should be enabled if there is a need to use HFP bluetooth devices with PulseAudio.

### orc
Pass the `-Dorc=enabled` option to the meson build script. Use the `liborc` library to execute CPU-agnostic SIMD code to improve CPU-intensive tasks, such as resampling.

It is recommended to enable this flag to improve performance.

### oss
Pass the `-Doss-output=enabled` option to the meson build script. Build and install the `module-oss` PulseAudio plugin that can be used to access sound hardware via the OSS (Open Sound System).

This flag should normally be disabled as the OSS is deprecated.

### selinux
Pull in the [sec-policy/selinux-pulseaudio](../sec-policy/selinux-pulseaudio.md) package as a dependency. Install SELinux policies to allow a PulseAudio daemon to properly run under a SELinux-restricted kernel.

This flag should only ever be toggle system-wide, i.e. as part of the SELinux-enabled portage profile.

### sox
Pass the `-Dsoxr=enabled` option to the meson build script. Use the `libsoxr` library to provide alternative resampling mechanisms. New resampling methods, the `soxr-mq`, `soxr-hq` and `soxr-vhq` can be accessed via the `resample-methods` configuration parameter.

This flag should be enabled if there is a need to resample sound before an output as it provides greater control and higher quality, however increases latency.

### ssl
Pass the `-Dopenssl=enabled` option to the meson build script. Build and install the `module-raop-discover` and the `module-raop-sink` plugins to stream audio data to products that support the RAOP (Remote Audio Output Protocol) protocol to provide Wireless Network Sound (aka Apple Airtunes) including mDNS/DNS-SD Service Discovery of RAOP devices.

This flag should only be enabled if there is a need to use RAOP protocol.

### system-wide
Install an `init.d` startup script and the SystemD service for the PulseAudio server and the configuration file for running the PulseAudio server in a system-wide mode. This mode is desgined for usage on thin client or embedded setups, where no real local user exists, where access is exclusively via the network, and where state data is flushed on each session termination.

This flag should normally be disabled.

### systemd
Pass the `-Dsystemd=enabled` option to the meson build script. Provide support for socket activation for PulseAudio server daemon under the SystemD init daemon and enable logging via the SystemD journal. Build and install the `module-systemd-login` PulseAudion plugin that creates a client for each login session of the user.

This flag should be enabled on the systems that use the SystemD init daemon.

### tcpd
Pass the `-Dtcpwrap=enabled` option to the meson build script. Enable support for the TCP wrappers (aka `tcpd`) tool to provide fine-grained control over network connections established to the PulseAudio server via an ACL system.

This flag should normally be disabled as TCP wrappers is obsolete and unmaintained.

### test
Pass the `-Dtests=true` option to the meson build script. Build the test suite provided with the source code and execute the `meson test` command after the main build is completed to run the tests and check for any regressions. This will extend the build time.

This flag should normally be disabled as these tests are mainly useful for developers, testers and the Gentoo team.

### udev
This flag only makes sense if the `alsa` or the `oss` flag is enabled. Pass the `-Dudev=enabled` option to the meson build script. Build and install the `module-udev-detect` PulseAudio plugin that allows to detect audio devices on the system using Udev.

This flag should normally be enabled on a regular desktop system.

### webrtc-aec
Pass the `-Dwebrtc-aec=enabled` option to the meson build script. Use the WebRTC Audio Processing module to provide microphone echo cancellation functionality. This support will be built into the `module-echo-cancel` PulseAudio plugin and can be accessed via the `aec_method` configuration parameter.

This flag should be enabled if there are multiple microphone recorders on the target system that can be used for the echo cancellation.

### X
Pass the `-Dx11=enabled` option to the meson build script. Build and install the `module-x11-bell`, `module-x11-publish`, `module-x11-xsmp` and the `module-x11-cork-request` plugins that provide access credentials to the PulseAudio server for the X clients, intercept X11 bell events and plays a sound on each occurence, register to the X11 session manager and synthesize X11 media key events. Install the `start-pulseaudio-x11` script that is used to automatically start the PulseAudio server via the XDG (X Desktop Group) autostart and load aforementioned modules.

This flag should only be enabled if the target system runs the X Server.

### zeroconf
Pass the `-Davahi=enabled` option to the configure script. Build and install the `module-zeroconf-publish` plugin to publish all local sinks and sources using mDNS Zeroconf to provide network auto-discovery support for the PulseAudio server.

This flag should only be enabled if there is a need to use Zeroconf.
