# gnome-base/gvfs

### afp
Pass the `--enable-afp` option to the configure script. Build and install the `gvfsd-afp` tool, that is used by the `gvfsd` daemon, to enable support for the AFP (Apple File Protocol) protocol via the `afp://` scheme.

This flag should be enabled if there is a need to use AFP.

### archive
Pass the `--enable-archive` option to the configure script. Build and install `gvfsd-archive` tool, that is used by the `gvfsd` daemon, to enable support for accessing an archive content through the VFS via the `archive://` protocol using the `libarchive` library. List of supported archive types depends on the flags enabled on the [app-arch/libarchive](../app-arch/libarchive.md).

It is safe to disable the flag.

### bluray
Pass the `--enable-bluray` option to the configure script. Provide an ability to mount Blu-ray filesystems from disks or images using the `libbluray` library.

This flag should be enabled if there is a need to access Blu-ray media.

### cdda
Pass the `--enable-cdda` option to the configure script. Use the `libcdio` library to provide an ability to mount and access Audio CDs via the `gvfsd-cdda` tool.

This flag should be enabled if there is a need to access contents of Audio CDs.

### elogind
Pass the `--enable-libelogind` option to the configure script. Use the `elogind` daemon to obtain seat and session information to make active GVfs mounts available to the specific session, making it work nicely in concurrent environment like multi-seat systems or terminal servers.

This flag should be enabled if the target system runs elogind.

### fuse
Pass the `--enable-fuse` option to the configure script. Build and install the `gvfsd-fuse` tool, that is used by the `gvfsd` daemon, to maintain a FUSE mount for making GVfs backends available to POSIX applications.

The flag should be enabled if there is a need to mount FUSE filesystems.

### gnome-keyring
Pass the `--enable-keyring` option to the configure script. Use the `libsecret` library to obtain authentication information, such as username, password or passphrase for network shares, servers or encrypted disks from the GNOME Keyring daemon.

This flag should be enabled if there is a desire to use GNOME Keyring for reading authentication info and secrets.

### gnome-online-accounts
Pass the `--enable-goa` option to the configure script. Build and install the `gvfs-goa-volume-monitor` daemon that uses the `libgoa` library to monitor and expose online storage services as a virtual filesystem or volume.

This flag should be enabled if there is a need to access online accounts via GVfs.

### google
Pass the `--enable-google` option to the configure script. Provide an ability to integrate with Google.Drive for accessing files via the virtual file system.

This flag should be enabled if there is a need to integrate with the Google.Drive storage.

### gphoto2
Pass the `--enable-gphoto2` option to the configure script. Build and install the `gvfsd-gphoto2` tool, that is used by the `gvfsd` daemon, to mount camera storage as a virtual filesystem via the PTP (Picture Transfer Protocol) using the `libgphoto2` library.

This flag should be enabled if there is a need to access cameras via GVfs.

### gtk
Pass the `--enable-gtk` option to the configure script. Build and install the `gvfsd-recent` tool, that is used by the `gvfsd` daemon, to provide access to recently used items through the `recent://` scheme.

This flag should be enabled to provide recently used items for file managers such as Nautilus or Nemo.

### http
Pass the `--enable-http` option to the configure script. Build and install the `gvfsd-http` and the `gvfsd-dav` backends, that are used by the `gvfsd` daemon, to provide an ability to mount VFS over the HTTP protocol, e.g. WebDav.

This flag should only be enabled if there is a need for the HTTP VFS access.

### ios
Pass the `--enable-afc` option to the configure script. Build and install the `gvfsd-afc` and `gvfs-afc-volume-monitor` tools, that are used by the `gvfsd` daemon to provide an access to iOS devices, such as iPhone or iPod Touch via the `afc://` protocol.

This flag should be enabled if there is a need to mount an iOS device storage via GVfs.

### mtp
Pass the `--enable-libmtp` and the `--enable-libusb` flags to the configure script. Buil and install the `gvfsd-mtp` tool, that uses the `libusb` and the `libmtp` libraries, to provide an acces to a media device's storage over the MTP (Media Transfer Protocol) via the `mtp://` scheme.

This flag should be enabled if there is a need to mount MTP devices using GVfs.

### nfs
Pass the `--enable-nfs` option to the configure script. Build and install the `gvfsd-nfs` tool, that uses the `libnfs` library, to enable an access to network shares over the  NFS (Network File System) protocol.

This flag should be enabled if there is a need to mount NFS shares with GVfs.

### policykit
Pass the `--enable-admin` option to the configure script. Build and install the `gvfsd-admin` backend that uses polkit framework to gain elevated privileges to provide an access to system files for a regular user via the `admin://` scheme.

This flag should be enabled on a modern GNOME environment, especially if it runs on top of the Wayland server.

### samba
Pass the `--enable-samba` option to the configure script. Build and install the `gvfsd-smb` and the `gvfsd-smb-browse` backends that provide an ability to browse and access Windows or Samba file shares over the SMB (Server Message Block) protocol.

This flag should be enabled if there is a need to access SMB shares.

### systemd
Pass the `--enable-libsystemd-login` option to the configure script. Integrate GVfs daemon with the SystemD LoginD service to obtain seat and session information and make active mounts available to the specific session, making it work nicely in concurrent environment like multi-seat systems or terminal servers.

This flag should be enabled for systems that use SystemD as their init daemon.

### test
Execute the `make check` command, when the main build is completed, to run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers or developers.

### udev
Pass the `--enable-udev` and the `--enable-gudev` options to the configure script. Integrate with Udev to provide an ability for various GVfs backends to discover devices and query information about them.

This flag should be enabled as a requirement for other backends.

### udisks
Pass the `--enable-udisks2` option to the configure script. Build and install the `gvfs-udisks2-volume-monitor` daemon that uses Udisks daemon to provide discovery and access for the disks, media, mounts and fstab entries. Enable support for the `x-gvfs-show`, `x-gvfs-name`, `x-gvfs-icon` and other options in the `fstab` config file. GVfs will also respect Udisks-specific opitons in Udev, e.g. `UDISKS_AUTO`, `UDISKS_SYSTEM`, etc.

This flag should be enabled on desktop systems with Desktop environments to display locally connected media in file manager, such as Thunar, Nautilus, Nemo or others.

### zeroconf
Pass the `--enable-avahi` option to the configure script. Build and install the `gvfsd-dnssd` backend that uses the `libavahi` library to discover and access devices and services on the network that advertise themselves through DNS-SD (DNS Service Discovery) protocol.

This flag should be enabled if there is a need to access DNS-SD enabled devices.
