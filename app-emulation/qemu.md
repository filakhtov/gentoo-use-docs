# app-emulation/qemu

### accessibility
Doesn't apply when building user emulation mode. Pass the `--enable-brlapi` option to the configure script. Use the `libbraille` library to communicate with `BRLTTY` daemon via the `BrlAPI` and provide access to the *nix console (text mode) for using a refreshable or fake (on-screen emulator) braille display. Enable support for `braille` option for the `-usbdevice` commandline option and the `usb_add` monitor command.

It is safe to disable the flag.

### aio
Doesn't apply when building user emulation mode. Pass the `--enable-linux-aio` option to the configure script. Use the `libaio` library to enable asynchronous input/output operations for storage using the Linux native AIO mechanism. Enable support for the `aio=native` parameter for the `-drive` option. Linux AIO performs better for images on the host filesystem, however might cause corruption on sparse images (if they aren't preallocated).

This flag can be enabled to improve performance when running from virtual images, however care should be taken to avoid data loss.

### alsa
Append `alsa` to the `--audio-drv-list=` option that is passed to the configure script. Provide an ability to use the ALSA (Advance Linux Sound Architecture) stack directly for capturing and playing sound inside of a virtual machine through an emulated sound card. ALSA backend can be selected by setting the `QEMU_AUDIO_DRV` environment variable to `alsa`.

This flag should be enabled if the host system uses ALSA on its own for handling audio.

### bluetooth
Doesn't apply when building user emulation mode. Pass the `--enable-bluez` option to the configure script. Use the `libbluetooth` library to provide an access to host Bluetooth HCI devices by passing commands and events to and from physical device identified by the name id, e.g. `hci0`. Enable support for the `hci,host[:id]` parameter for the `-bt` command line option.

This flag should only be enabled if there is a need to access host's Bluetooth devices from virtual machines.

### bzip2
Doesn't apply when building user emulation mode. Pass the `--enable-bzip2` option to the configure script. Use the `libbzip2` library to provide support for the bzip2 compression algorithm for reading DMG (aka Apple Disk) images compressed with bzip2.

This flag can be safely disabled if there is no need to access DMG images.

### caps
Doesn't apply when building user emulation mode. Pass the `--enable-cap-ng` option to the configure script. Use the `libcap-ng` library to drop elevated privileges for various helpers:

- `qemu-pr-helper` will provide `-u` and `-g` options to specify user and group to switch to, when root permissions are no longer needed;
- `qemu-bridge-helper` when running with the `suid` bit enabled will drop all capabilities but preserve `CAP_NET_ADMIN` and switch to unprivileged user;

It is recommended to enable this flag if QEMU to be used with a network bridge or pass through SCSI device, to improve security.

### capstone
Doesn't apply when building user emulation mode. Pass the `--enable-capstone` option to the configure script. Use the `libcapstone` library to provide an ability to disassemble host or target binary code for the debugging purposes via the Capstone disassembly framework.

This flag should only be enabled if there is a need to debug binary code translation.

### curl
Doesn't apply when building user emulation mode. Pass the `--enable-curl` option to the configure script. Enable support for remote block devices using the `libcurl` library. Provide an ability to use remote disk images (in read-only mode) over HTTP(S)/FTP(S) protocols, and enables a set of relevant parameters for the `--drive` command line option, including: `protocol`, `username` and `password`, `host`, `path`, `url`, etc.

It is safe to disable the flag if there is no need to access remote disks.

### debug
Pass the `--enable-debug-info` and the `--enable-debug-tcg` options to the configure script. Produce libraries and binaries with debugging symbols included. Enable TCG (Tiny Code Generator) debugging, e.g. enable assertions, perform additional checks on registers and print debugging information, report temporaries cleaning issues, etc.

This flag should only ever be enabled for debugging purposes as it has performance penalties.

### doc
Pass the `--enable-docs` option to the configure script. This flag currently does nothing and exists only as a path forward for QEMU project to migrate their documentation to Sphinx Python generator.

This flag should be disabled.

### fdt
Doesn't apply when building user emulation mode. Pass the `--enable-fdt` option to the configure script. Use the `libfdt` library provided by the DTC (Device Tree Compiler) to generate device tree blob for different platforms. aarch64, arm, ppc, microblaze, mips64el and riscv emulated machines require this to function, but other platforms can use it too, e.g. ACPI FDT on x86.

It is recommended to enable this flag.

### filecaps
Set the `CAP_NET_ADMIN` capability on the `qemu-bridge-helper` binary before installing it. This provides necessary elevated permissions for the helper to modify network bridge devices while running as an unprivileged user, and allows to avoid setting the `suid` flag on the `qemu-bridge-helper` to improve security.

It is recommended to enabled this flag instead of the `caps` one when there is no need to use the `qemu-pr-helper`.

### glusterfs
Doesn't apply when building user emulation mode. Pass the `--enable-glusterfs` option to the configure script. Enable the GlusterFS block driver that uses `libgfapi` library to avoid FUSE overhead when working with virtual machine images on gluster volumes. Provide support for the `gluster://` protocol for the `file=` parameter of the `-drive` command line option.

This flag should only be enabled if there is a need to use QEMU with GlusterFS volumes.

### gnutls
Doesn't apply when building user emulation mode. Pass the `--enable-gnutls` and `--enable-nettle` options to the configure script. Provide an ability to use the GnuTLS library with the Nettle backend for TLS encryption in VNC, AES for qcow2 native encryption, single DES in the VNC server for password authentication, SHA256 hashing in the quorum block driver, SHA1 hashing in the VNC websockets handshake, TLS support on network backends, etc. Enable support for the `tls` and `x509` parameters for `-vnc` command line option.

This flag should be enabled if there is a need to use cryptographic routines and TLS support.

### gtk
Doesn't apply when building user emulation mode. Pass the `--enable-gtk` and the `--with-gtkabi=3.0` option to the configure script. Use the GTK+ version 3.x library to display video output from virtual machine in a GTK window. Enable support for the `gtk` value for the `-display` command line option.

It is safe to disable the flag when e.g. when using `-nographic` option with VGA pass-through, VNC or Spice, or using SDL to access virtual machine video output.

### gtk2
Only works together with the `gtk` flag. Pass the `--with-gtkabi=2.0` (instead of `3.0`) option to the configure script. Same as the `gtk` flag, but use GTK+ version 2.x instead.

This flag should only be enabled if there is a need for a GTK+ display output on top of the GTK+ library of 2.x version.

### infiniband
Doesn't apply when building user emulation mode. Pass the `--enable-rdma` option to the configure script. Use the OpenFabrics `librdmacm`, `libibverbs` and `libibumad` libraries to enable live migration of the virtual machines via the RDMA (Remote Direct Memory Access) even if a machine is under heavy load. Enable support for the `rdma:` parameter for both: the `-incoming` command line option and the `migrate` monitor command.

Enable this flag if there is a need to use an RDMA-based migration.

### iscsi
Doesn't apply when building user emulation mode. Pass the `--enable-libiscsi` option to the configure script. Use the `libiscsi` library to provide support for the iSCSI (Internet Small Computer Systems Interface) storage networking standard. Enable built-in iSCSI initiator for attaching iSCSI volumes as virtual machine block devices by directly connecting guest storage interfaces to an iSCSI target LUN, bypassing the need for any host iSCSI initiator configuration. Provide support for the `iscsi:` protocol of the `file` parameter for the `-drive` command line option.

This flag should be enabled if there is a need to use iSCSI volumes as block devices for the virtual machines.

### jpeg
Doesn't apply when building user emulation mode and only works when the `vnc` flag is enabled. Pass the `--enable-vnc-jpeg` option to the configure script. Enable support for the JPEG lossy compression method for transmitting virtual machine display output via the VNC protocol.

This flag should be enabled when using VNC over slow networks, however depending on settings, image quality might be low.

### lzo
Doesn't apply when building user emulation mode. Pass the `--enable-lzo` option to the configure script. Use the `liblzo2` library to provide an ability to compress virtual machine memory dumps using the LZO compression method, e.g. via `kdump-lzo` option for the `dump-guest-memory` QMP command.

This flag should only be enabled if there is a need to dump virtual machine memory for debugging purposes and LZO compression is desired.

### ncurses
Doesn't apply when building user emulation mode. Pass the `--enable-curses` option to the configure script. Use the `libncursesw` library to display VGA output when in text mode using a (n)curses interface, instead of using SDL or other graphical libraries. Enable support for the `-curses` command line option.

This flag can be useful for displaying text-only display output in host console.

### nfs
Doesn't apply when building user emulation mode. Pass the `--enable-libnfs` option to the configure script. Use the `libnfs` library to provide an ability to use NFS (Network File System) exports as virtual machine block devices and enable the `nfs:` protocol for the `file` parameter of the `-drive` command line option to do so. Note, that from guest standpoint block device will appear to be locally attached.

This flag should only be enabled if there is a need to use NFS exports as guest block devices.

### nls
Install translation po files for all available locales and provide an ability to translate programs messages and output into different languages based on system locale settings. When disabled, remove all locale files making English the only available language for QEMU.

This flag can be safely disabled if there is no need to use QEMU in a non-English language.

### numa
Doesn't apply when building user emulation mode. Pass the `--enable-numa` option to the configure script. Use the `libnuma` library to provide an ability to simulate a multi node NUMA (non-uniform memory access) system and enable support for the `-numa` command line option to configure settings.

This flag should only ever be enabled if there is a need to simulate a NUMA system.

### opengl
Doesn't apply when building user emulation mode. Pass the `--enable-opengl` option to the configure script. Use the EGL API of the Mesa 3D library to enable OpenGL hardware acceleration for rendering guest display output onto the surface inside of an SDL or GTK+ user interface. Enable support for the `gl` parameter of the `-display` command line option.

This flag should be enabled if there is a need for OpenGL hardware acceleration in a UI, and is recommended when using VirGL acceleration inside of a guest machine and displaying output through SDL or GTK+ UI.

### pin-upstream-blobs
Enforce specific versions and ensure that `binary` flag is enabled on firmware package dependencies to pull in prebuilt files recommended by the upstream maintainer. This also means that there is no way to apply a patch or modify a source before installation. When disabled, firmware files will be built from source. Note, that upstream maintainer won't likely accept bug reports if using non-recommended versions.

It is recommended to enable this flag for maximum compatibility and stability.

### png
Doesn't apply when building user emulation mode. Pass the `--enable-vnc-png` option to the configure script. Enable support for the PNG lossless compression method for transmitting virtual machine display output via the VNC protocol.

This flag should be enabled when using VNC over fast networks or when high quality image output is required.

### pulseaudio
Append `pa` to the `--audio-drv-list=` option that is passed to the configure script. Provide an ability to use the PulseAudio sound server for capturing and playing sound inside of a virtual machine through an emulated sound card. PulseAudio backend can be selected by setting the `QEMU_AUDIO_DRV` environment variable to `pa`. Enables support for the `QEMU_PA_` environment variables.

This flag should be enabled if the host system uses PulseAudio for accessing audio hardware.

### python
For every active Python target install:

- `qmp.py` - a script to communicate with QEMU instances over the QMP (QEMU Machine Protocol) protocol;
- `vmxcap` - a tool for querying VMX capabilities;
- `qmp-shell` - provides a shell to communicate with QEMU instance over the QMP protocol;
- `qemu-ga-client` - a client for QEMU Guest Agent to provide an access to QMP commands and events that terminate and originate respectively within the guest;

It is safe to disable the flag.

### rbd
Doesn't apply when building user emulation mode. Pass the `--enable-rbd` option to the configure script. Use the `librbd` library to access Ceph's RBDs (RADOS Block Devices) to provide volumes for virtual machines. Enable support for the `rbd:` value of the `file` parameter of the `-drive` command line option.

This flag should only be enabled if there is a need to access Ceph's/RADOS block devices.

### sasl
Doesn't apply when building user emulation mode and only works if the `vnc` flag is enabled. Pass the `--enable-vnc-sasl` option to the configure script. Enable SASL (Simple Authentication and Security Layer) authentication method - an extension for VNC, that provides an easily extendable, pluggable authentication method, and allows for integration with a wide range of authentication mechanisms, such as PAM, GSSAPI/Kerberos, LDAP, SQL databases, one-time keys, etc. Provide support for the `sasl` parameter of the `-vnc` command line option.

This flag should be enabled if there is a need for the SASL-based authentication.

### sdl
Doesn't apply when building user emulation mode. Pass the `--enable-sdl` and `--with-sdlabi=1.2` option to the configure script. Use the `libsdl` version 1.2 library to display video output from virtual machine (usually in a separate window) and enable support for the `sdl` value for the `-display` command line option to do so. Provide an ability to capture and play audio via the SDL (Simple DirectMedia Layer) backend through an emulated sound card. The SDL backend can be selected by setting the `QEMU_AUDIO_DRV` environment variable to the `sdl` value.

It is recommended to enable this flag together with the `sdl2` flag if there is a need to display an output through the SDL library.

### sdl2
Only works if the `sdl` flag is enabled. Pass the `--with-sdlabi=2.0` (instead of `1.2`) option to the configure script. Does the same as the `sdl` flag, but uses the `libsdl2` library instead, which is a recent and non-deprecated SDL library version.

It is recommended to enable this flag, if there is a need to display an output through the SDL library.

### seccomp
Doesn't apply when building user emulation mode. Pass the `--enable-seccomp` option to the configure script. Enable the seccomp (secure computing mode) syscall filtering facility. Prior to QEMU version 2.11 seccomp had a single giant whitelist of excluded syscalls to allow every feature to work properly, however it was still causing issues with third-party libraries. Newer versions of QEMU, however have modular blacklists and causes almost no issues, so can be safely disabled to improve security.

This flag can be enabled on modern versions of the QEMU emulator to improve security.

### selinux
Pull the [sec-policy/selinux-qemu](../sec-policy/selinux-qemu.md) package as a dependency that provides SELinux policies necessary for properly running QEMU under a SELinux-restricted kernel.

This flag should only ever be toggled system-wide, i.e. as part of the SELinux-enabled Portage profile.

### smartcard
Doesn't apply when building user emulation mode. Pass the `--enable-smartcard` option to the configure script. Use the `libcacard` library to provide support for smart cards. Make two additional devices available:

- `ccid-card-passthru` - uses the passthru protocol to connect to remote computer carrying physical or virtual smartcard;
- `ccid-card-emulated` - provides an emulated card using the NSS backend with certificates or real hardware on QEMU running host;

This flag should only be enabled if there is a need to support smart cards.

### snappy
Doesn't apply when building user emulation mode. Pass the `--enable-snappy` option to the configure script. Use the `libsnappy` library to enable support for snappy (formerly Zippy) compression format when creating memory dumps from guest virtual machines, e.g. using `kdump-snappy` option for the `dump-guest-memory` command over QMP.

This flag can be safely disabled.

### spice
Doesn't apply when building user emulation mode. Pass the `--enable-spice` option to the configure script. Use the `libspice` library to provide client access to remote displays and devices (e.g. keyboard, mouse, audio) on virtual machines, including the support for copy and paste from host via the Spice protocol. Enable support for the `-spice` command line option. Provide an ability to redirect audio from virtual sound card to the Spice client, by passing the `spice` value to the `QEMU_AUDIO_DRV` environment variable.

This flag should be enabled if there is a need for remote desktop access to virtual machines.

### ssh
Doesn't apply when building user emulation mode. Pass the `--enable-libssh2` option to the configure script. Use the `libssh2` library to enable support for the SFTP (SSH File Transfer Protocol). Provide an ability to access guest block device images located on a remote server over the SSH protocol. Enable support for the `ssh` protocol for the `file` parameter of the `-drive` command line option.

This flag should only be enabled if there is a need to access block device images over an SFTP protocol.

### static
Pass the `--static` and `--disable-pie` options to the configure script when building non-user emulation mode binaries. Append the `-static` option to the `LDFLAGS` variable and disable building PIE code to produce statically linked `qemu-system-*` binaries.

This flag should only be ever enabled if there is an explicit need for the static binaries.

### static-user
Pass the `--static` and `--disable-pie` options to the configure script when building user emulation mode binaries. Append the `-static` option to the `LDFLAGS` variable and disable building PIE code to produce statically linked `qemu-user-*` binaries.

This flag should only be ever enabled if there is an explicit need for the static binaries.

### systemtap
Pass the `--enable-trace-backend=dtrace` option to the configure script. Enable DTrace SDT (statically defined probes) to analyze behavior and performance issues (potentially even on the production system) without using debugger. DTrace backend was only tested with SystemTap.

It is safe to disable the flag.

### tci
Pass the `--enable-tcg-interpreter` option to the configure script. Enable TCI (Tiny Code Generator (aka TCG) Interpreter) that allows running QEMU on almost any 32 or 64 bit host. Without TCI it can only produce native code for the most important architectures, i.e. x86, arm, mips, ppc, s390 and sparc. Using an interpreter for the generated bytecode, however, it is possible to support any host. Note that TCI support is be experimental and might be unstable and/or slow.

This flag should be enabled if the host system is not on the list supported by the TCG.

### test
Disable PaX MPROTECT restrictions by setting an `m` flag on the `qemu-system-*` binaries to prevent `grsec: denied RWX mmap ...` error when running tests under a PaX restricted kernel. Execute the `make check` command and `make check-report.html` after the main build is completed to run the test suite provided with the source code and generate an HTML test result.

This flag should normally be disabled as it is primarily used by the Gentoo team, testers and developers.

### usb
Doesn't apply when building user emulation mode. Pass the `--enable-libusb` option to the configure script. Use the `libusb` library to support host usb devices redirection and provide an ability to detach actual USB devices connected to the host machine and connect them to the guest machine, aka USB pass-through. Enable support for the `usb-host` parameter of the `-device` command line option to achieve this.

This flag should be enabled to support USB device pass-through.

### usbredir
Doesn't apply when building user emulation mode. Pass the `--enable-usb-redir` option to the configure script. Use the `libusbredirparser` library to support the usbredir network protocol for sending USB device traffic over a network connection. This is currently used with the Spice protocol to allow USB device redirection from host machine into the guest machine. Enable support for the `usb-redir` parameter of the `-device` command line option.

This flag should be enabled if there is a need to forward USB devices to the guest machine over the usbredir protocol.

### vde
Doesn't apply when building user emulation mode. Pass the `--enable-vde` option to the configure script. Use the `libvdeplug` library to provide support for the VDE (Virtual Distributed Ethernet) network backend. VDE is a full Ethernet emulation and can be used to interconnect virtual and real machines, both local and remote, usually for testing purposes. Enable support for `vde` parameter of the `-net` and `-netdev` command line options.

This flag can be enabled for lab testing purposes or network simulation.

### vhost-net
Doesn't apply when building user emulation mode. Pass the `--enable-vhost-net` option to the configure script. Enable vhost-net offload mechanism for virtio-net network device. This requires a host kernel with `CONFIG_VHOST_NET` and `CONFIG_PCI_MSI` options enabled. The vhost-net module enables KVM (QEMU) to offload the servicing of virtio-net devices to the vhost-net kernel module, reducing the context switching and packet copies in the virtual dataplane. Enable support for the `vhost=on` parameter of the `-netdev` command line option for the `virtion-net` adapter.

This flag can be enabled to improve network performance (up to 8x faster than normal virtio), however might have issues with some DHCP clients.

### virgl
Doesn't apply when building user emulation mode. Pass the `--enable-virglrenderer` option to the configure script. Enable support for OpenGL acceleration in the guest machine and allow some OpenGL calls to be directed to the host system's OpenGL driver for processing. Currently only Linux guest on a Linux host is supported (although Windows work is in progress). This also mean that only OpenGL can be supported and obviously no Direct3D. Enable the `virgl` parameter of the `-device` command line option for the `virtio-vga` graphics adapter.

It is safe to disable the flag, however it can be used for OpenGL acceleration for a Linux guest running on a Linux host.

### virtfs
Doesn't apply when building user emulation mode. Pass the `--enable-virtfs` option to the configure script. Enable support for the VirtFS - a new paravirtualized filesystem interface designed for improving passthrough technologies in the KVM environment. It is based on the VirtIO framework and uses the 9P protocol. It provides virtualization aware filesystem, offers paravirtualized system services and simple passthrough for directories from host to guest. Only works for a Linux guest running on a Linux host. Enable the `virtio-9p-pci` device for the `-device` command line option.

It is safe to disable the flag.

### vnc
Doesn't apply when building user emulation mode. Pass the `--enable-vnc` option to the configure script. Provide an ability to listen on a specified VNC display and redirect the virtual machine VGA output over the VNC session and enable support for the `-vnc` command line option to configure it.

It is safe to disable the flag if QEMU to be used with any other video output, such as GTK+, SDL, Spice, etc.

### vte
Doesn't apply when building user emulation mode and should only be enabled if the `gtk` flag is enabled. Pass the `--enable-vte` option to the configure script. Enable the VTE (Virtual Terminal Emulator) support for the GTK+ user interface to provide an access to QEMU monitor and serial/console devices of the guest machine.

This flag can be disabled if there is no need to use GTK+ UI or QEMU monitor.

### xattr
Pass the `--enable-attr` option to the configure script. Use the `libattr` library to support XATTRs (eXtended ATTRibutes). XATTR support is necessary for VirtFS filesystem and can also be used by user mode QEMU tools to properly handle extended attributes when executing a syscall for emulated Linux platform.

This flag should be enabled if there is a need to use the VirtFS filesystem or run user mode emulation on filesystem with XATTR support.

### xen
Doesn't apply when building user emulation mode. Pass the `--enable-xen` and `--enable-xen-pci-passthrough` options to the configure script. Enable QEMU integration with Xen to emulate a part of the hardware, in particular a disk, a network card and the graphic output, so a guest does not need to be modified in order to run under Xen. Even with a modified guest, QEMU can be used to handle the graphic output of the guest, or as a backend for a paravirtualized disk or network card. Enable support for Xen PCI pass-through to attach real PCI devices to Xen guest virtual machines.

This flag should only be enabled if there is a need to use QEMU with Xen.

### xfs
Doesn't apply when building user emulation mode. Pass the `--enable-xfsctl` option to the configure script. Enable improved support for the XFS filesystem, e.g. `xfsctl()` notification and synchronizing data for virtual disks located on the XFS volumes.

It is highly recommended to enable this flag if there is a need to use virtual disk images stored on the XFS to avoid data corruption, otherwise it should be disabled.
