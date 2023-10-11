# media-video/pipewire

### bluetooth
Pass the `-Dbluez5=enabled`, `-Dbluez5-backend-hsp-native=enabled`, `-Dbluez5-backend-hfp-native=enabled`, `-Dbluez5-backend-ofono=enabled`, `-Dbluez5-backend-hsphfpd=enabled`, `-Dbluez5-codec-aac=enabled`, `-Dbluez5-codec-aptx=enabled`, `-Dbluez5-codec-ldac=enabled`, `-Dopus=enabled`, `-Dbluez5-codec-opus=enabled`, `-Dlibusb=enabled` options to the meson build script. Enable support for Bluetooth devices and a wide variety of audio codecs, such as HFP (Hands-Free Profile), HSP (Handset Profile), aptX, AAC (Advanced Audio Codec), LDAC, Opus.

This flag should only be enabled if there is a need to use Bluetooth audio devices.

### dbus
Pass the `-Ddbus=enabled` option to the meson build script. Enable D-Bus support, both to obtain realtime process capabilities using RTKit (Real-Time Kit) and expose a bunch of services related to Bluetooth and Flatpak Portals. It is also used by the `pw-reserve` tool to reserve or monitor a device on DBus.

It is safe to disable this flag.

### doc
Pass the `-Ddocs=enabled` option to the meson build script. Use Doxygen tool to generate and install the documentation in the HTML format. Documentation primarily contains documentation for developers, including the high level design of the project, examples of how to develop against PipeWire, description of functions and data structures, etc.

This flag should normally be disabled.

### echo-cancel
Pass the `-Decho-cance-webrtc=enabled` option to the meson build script. Enable support for real-time acoustic echo cancellation for communication apps using the WebRTC AEC algorithm.

It is safe to disable this flag.

### extra
Pass the `-Dpw-cat=enabled` and `-Dsndfile=enabled` options to the meson build script. Build and install the `pw-cat` (and its various aliases `pw-play`, `pw-record`, `pw-midiplay`, etc) - a simple tool for playing back or capturing raw or encoded media files on a PipeWire server using the `libsndfile` library.

This flag can be safely disabled.

### ffmpeg
Requires the `extra` flag to be enabled. Pass the `-Dpw-cat-ffmpeg=enabled` option to the meson build script. Enable FFmpeg integration in the `pw-cat` tool (and enables the `pw-encplay` alias) to provide an ability to play files encoded in various formats supported by FFmpeg.

It is safe to disable this flag.

### flatpak
Pass the `-Dflatpak=enabled` option to the meson build script. Enable support for identifying sandboxed clients running in Flatpak when they connect to the PipeWire server.

This flag should only be enabled if there is a need to use Flatpak applications with PipeWire.

### gsettings
Pass the `-Dgsettings=enabled` option to the meson build script. Provide an ability to access settings stored by the PulseAudio GSettings module to make the `paprefs` configuration tool work with PipeWire.

It is safe to disable this flag.

### gstreamer
Pass the `-Dgstreamer=enabled` and `-Dgstreamer-device-provider=enabled` options to the meson build script. Provide `pipewiresrc` and `pipewiresink` GStreamer elements that can be used in pipelines, as well as a device monitor that exposes PipeWire devices to GStreamer pipelines (e.g. in `gst-device-monitor`). This allows GStreamer-based devices to play and capture media via PipeWire.

This flag can be safely disabled.

### ieee1394
Pass the `-Dlibffado=enabled` option to the meson build script. Use the `libffado` library from the FFADO (Free FireWire Audio Drivers) project to provide support for FireWire devices. It is currently untested and is not considered stable.

This flag should normally be disabled.

### jack-client
Pass the `-Djack=enabled` option to the meson build script. Build and install the JACK (JACK Audio Connection Kit) SPA (Simple Plugin API) plugin that provides an ability for PipeWire to act as a JACK client, sending the audio streams to the native JACK daemon, instead of directly to the hardware.

It is safe to disable this flag.

### jack-sdk
Pass the `-Djack-devel=true` option to the meson build script. Install JACK development files (headers), to avoid relying on external JACK development package.

This flag can be safely disabled.

### liblc3
Pass the `-Dbluez5-codec-lc3` option to the meson build script. Enable support for Bluetooth LC3 (Low Complexity Communication Codec) introduced in Bluetooth 5.2 that supports Bluetooth LE Audio standard and aims to replace the SBC (Subband Codec) codec.

This flag should only be enabled if there is a need to use LC3-enabled Bluetooth devices with PipeWire.

### lv2
Pass the `-Dlv2=enabled` option to the meson build script. Enable support for [LV2](https://lv2plug.in/) audio plugins.

It is safe to disable this flag.

### modemmanager
Pass the `-Dbluez5-backend-native-mm=enabled` option to the meson build script. Use ModemManager to enhance native HFP (Hands-Free protocol) support, allowing to accept, reject or hangup the call, dial a number, query operator name, access the call list and various other functions.

This flag can be safely disabled.

### pipewire-alsa
Pass the `-Dpipewire-alsa=enabled` option to the meson build script. Install PipeWire configuration hook for ALSA. This allows any applications that natively use ALSA to transparently use PipeWire instead, avoiding the exclusive usage of sound devices and allowing to multiplex sound.

It is safe to disable this flag.

### readline
Pass the `-Dreadline=enabled` option to the meson build script. Use the `libreadline` library to enable history and completion in the `pw-cli` tool.

This flag can be safely disabled.

### roc
Pass the `-Droc=enabled` option to the meson build script. Enable support for ROC - a toolkit for real-time audio streaming over the network. PipeWire supports both being a sender and a receiver for the audio stream.

It is safe to disable this flag.

### sound-server
Install a bunch of configuration files to use PipeWire as a sound server. Display information on how to enable and use PipeWire in a user session to replace PulseAudio after the installation is completed.

This flag should normally be enabled on desktop systems.

### ssl
Pass the `-Draop=enabled` option to the meson build script. Enable RAOP (Remote Audio Output Protocol) module - an internet streaming protocol based on RTSP / RTP created by Apple that powers their AirPlay technology, allowing PipeWire to play audio through AirPlay enabled devices.

It is safe to disable this flag.

### system-service
Pass the `-Dsystemd-system-service=enabled` option to the meson build script. Install a system-wide systemd unit that enables PipeWire to run as a system service (instead of the per-user-session instance) and a set of basic configuration files.

This flag should normally be disabled, because system-wide mode requires configuration and won't work out of the box and is also meant for specific use cases, such as embedded systems.

### systemd
Pass the `-Dsystemd=enabled` and `-Dsystemd-user-service=enabled` options to the meson build script. Enable support for systemd and install user-specific systemd service and socket files to activate PipeWire on a per-user session basis.

This flag should only be enabled system-wide as part of the systemd-enabled Portage profile.

### test
Pass the `-Dtests=enabled` option to the meson build script. Build a test suite provided with the source code and execute the `meson test` command after the main build is completed to run it and check for any regressions. This will extend the build time.

This flag should normally be disabled, because the test suite is primarily oriented towards the developers, maintainers and testers.

### v4l
Pass the `-Dv4l2=enabled` option to the meson build script. Enable the V4L2 (Video 4 Linux) SPA plugin that provides controlled access to v4l2 devices and allows to share one device between multiple processes.

It is safe to disable this flag.

### X
Pass the `-Dx11=enabled`, `-Dx11-xfixes=enabled` and `-Dlibcanberra=enabled` options to the meson build script. Build and install the X11 Bell module that intercepts the X11 bell events and uses libcanberra to play a sound through PipeWire in response.

This flag can be safely disabled.

### zeroconf
Pass the `-Davahi=enabled` option to the meson build script. Provide an ability to automatically discover devices to send audio to, and advertise PipeWire as a a device that can play audio using zeroconf/mDNS/Bonjour.

It is safe to disable this flag.
