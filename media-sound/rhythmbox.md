# media-sound/rhythmbox

### cdr
Pass the `--with-brasero` option to the configure script. Build and install the Audio CD Recorder plugin that uses the `libbrasero` library to rip Audio CDs from media library playlists.

It is safe to disable the flag.

### daap
Pass the `--enable-daap` option to the configure script. Build and install the DAAP Music Sharing plugin that uses the `libdmapsharing` library to share music and play shared music on a local network over the DAAP (Digital Audio Access Protocol) protocol.

This flag should be enabled if there is a need to access music shared over the DAAP protocol, e.g. from Apple iTunes.

### dbus
Pull in the [sys-apps/dbus](../sys-apps/dbus.md) package as a dependency. D-Bus package is required by the `MediaServer2 D-Bus interface` plugin, that provides an implementation of the MediaServer2 D-Bus interface specification and allows out-of-process media streams to be exposed to other apps, and `MPRIS D-Bus interface` plugin, that provides an implementation of the MPRIS (Media Player Remote Interfacing Specification) D-Bus interface specification that enables a mechanism for discovery, querying and basic playback control of Rhythmbox through D-Bus, e.g. to control the player from a notification tray or a command-line interface.

This flag should be enabled to provide an ability to interact with Rhythmbox over the D-Bus interface.

### gnome-keyring
Pass the `--with-libsecret` option to the configure script. Use the `libsecret` library to provide an ability to access GNOME keyring to store and obtain authentication information when accessing media over the DAAP protocol.

This flag should only be enabled together with the `daap` flag and if there is a need to save passwords for protected DAAP shares.

### ipod
Pass the `--with-ipod` option to the configure script. Build and install the `Portable Players - iPod` plugin that uses the `libgpod` library to enable support for Apple iPod or iPhone devices, e.g. transfer media to a player, display a content on a device, play music from device, etc. Note: support is very limited and newer iOS versions might not be properly supported.

This flag should only be enabled if there is a need to access Apple devices.

### libnotify
Pass the `--enable-libnotify` option to the configure script. Build and install the `Notification` plugin that uses the `libnotify` library to enable notification popups, such as playback start, stop, pause, etc.

It is safe to disable the flag.

### lirc
Pass the `--enable-lirc` option to the configure script. Build and install the `LIRC` plugin, that allows to control Rhythmbox using an infrared remote control using the LIRC (Linux Infra-red Remote Control) library.

This flag should only be enabled if there is a need to use infrared remote controls to control the player.

### mtp
Pass the `--enable-mtp` option to the configure script. Build and install the `Portable Players - MTP` plugin, that uses the `libmtp` library to enable support for MTP devices, e.g. show the content, transfer, play from device, and so forth.

This flag should be enabled if there is a need to support MTP devices through Rhythmbox.

### python
Prepare Python environment for the configure script to pick up the correct version. Pass the `--enable-python` option to the configure script. Build and install the following Python-based plugins:

- `Context Pane` that shows information related to the currently playing artist and song;
- `Web remote control` that provides an ability to control Rhythmbox remotely from a web browser;
- `SoundCloud` to browse and play sounds from SoundCloud;
- `Send tracks` that allows to send selected tracks by email;
- `ReplayGain` normalization plugin that uses the ReplayGain technique to provide a consistent playback volume, i.e. achieve the same perceived playback loudness of audio files;
- `Zeitgeist` to provide information about played tracks and activity to Zeitgeist service;
- `Python Console` plugin that provides interactive python console, that can be used to script Rhythmbox, alter its behavior, create plugins, etc;
- `Magnatune Store` that adds support for playing and purchasing music from the Magnatune online music store;
- `Song Lyrics` to fetch song lyrics from the Internet;
- `IM Status` to update instant messengers status according to the current playing song (supports Empathy and Pidgin);
- `Cover art search` to find and fetch album covers from the Internet;

This flag should be enabled if any of the aforementioned plugins is needed. Unnecessary plugins can be easily disabled through the "Plugins" menu of the Rhythmbox.

### test
Compile GSettings XML schemas necessary for running test. Start a new Xvfb session and execute the `make check` command inside of it. Run the test suite provided with the source code. This will extend a build time.

This flag should normally be disabled. It is oriented to the Gentoo team, testers and developers.

### udev
Pass the `--with-gudev` option to the configure script. Use the `libgudev` library to access the Udev device manager to detect and identify audio player devices (Apple iPod/iPhone and MTP devices), and build and install the `Android devices` plugin, that provides an Android 4.0 (and later) specific device handling via the MTP protocol.

This flag should be enabled if there is a need to access audio players and mobile devices.

### upnp-av
Pass the `--enable-grilo` option to the configure script. Build and install the `Grilo media browser` plugin that uses the Grilo UPnP AV plugin to provide an ability to browse various local and Internet media sources, including uPnP/DLNA media servers.

This flag should be enabled if there is a need to browse and access UPnP AV servers.
