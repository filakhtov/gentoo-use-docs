# app-emulation/libvirt

### apparmor
Pass the `-Dapparmor=enabled` and `-Dapparmor_profiles=true` options to the meson build script. Build the `virt-aa-helper` binary and install it together with AppArmor profiles. A set of profiles installed allows the `libvritd` to run virtual machines under AppArmor-enabled kernel and the binary is responsible for compiling per-vm specific set of policies, allowing the VM to only access its resources, such as drives, images, etc.

This flag should only be enabled system-wide and only if the system has an AppArmor enabled kernel.

### audit
Pass the `-Daudit=enabled` option to the meson build script. Enable support for the Linux Audit framework to collect and report information about important operations performed through the host's audit subsystem. This provides a canonical historical record of changes to virtual machines' and continers' lifecycle states and their configuration. Auditing is supported by QEMU/KVM and LXC backends.

This flag can be safely disabled, if there is no need for auditing support.

### caps
Pass the `-Dcapng=enabled`, `-Dqemu_user=qemu` (`root` when the flag is disabled) and `-Dqemu-group=qemu` (`root` if the flag is disabled) options to the meson build script. Use the `libcap-ng` library to allow dropping process capabilities when running QEMU virtual machines as a `root` user, and is required to configure LXC domains when running containers.

It is recommended to enable this flag if there is a need to run QEMU virtual machines using the `root` user and can be safely disabled otherwise.

### dbus
Pass the `-Ddbus=enabled` option to the meson build script. Build and install the `libvirt-dbus` library that wraps an API provided by the `libvirt` library and exposes the D-Bus API on top of it.

This flag should be enabled if there is a need for the `libvirt` D-Bus API.

### dtrace
Pass the `-Ddtrace=enabled` option to the meson build script. Enable DTrace static probes in both the client and server code to provide an ability to analyze RPC messages that are being sent and received during the clien-server communication.

This flag should normally be disabled, unless there is a need to perform communication tracing, e.g. for debugging purposes.

### firewalld
Add the `firewalld` dependency to the `libvirtd` OpenRC init script. Pass the `-Dfirewalld=enabled` option to the meson build script. Provide an ability for `libvirt` to place the bridge interface of a virtual network into the specified `firewalld` zone (`libvirt` by default) to apply all the rules of the zone to the virtual machine traffic.

This flag can be safely disabled, and should be enabled if there is a need to seamlessly integrate with `firewalld`.

### fuse
Pass the `-Dfuse=enabled` option to the meson build script. Use the FUSE (Filesystem in Userspace) to provide virtualized `/proc` mount for LXC containers.

This flag can be safely disabled, unless there is a need to run LXC containers.

### glusterfs
Pass the `-Dglusterfs=enabled` and `-Dstorage_gluster=enabled` options to the meson build script. Enable support for the GlusterFS distributed network filesystem as a storage pool for virtual machines.

It is safe to disable the flag when no GlusteFS support is needed.

### iscsi
Add the `iscsid` dependency to the `libvirtd` OpenRC init script. It is an alternative for the `iscsi-direct` flag. Pass the `-Dstorage_iscsi=enabled` option to the meson build script. Use the `iscsiadm` utility to provide an ability to use iSCSI targets as a storage pool for virtual machines.

This flag can be safely disabled if no iSCSI network storage pool is required.

### iscsi-direct
This flag is an alternative for the `iscsi` flag. Pass the `-Dstorage_iscsi_direct=enabled` option to the meson build script. Use the `libiscsi` library to provide an ability to use iSCSI targets as a storage pool for virtual machines.

It is safe to disable the flag if no iSCSI network storage pool is required.

### libssh
Pass the `-Dlibssh=enabled` option to the meson build script. Use the `libssh` library to provide an access to the `libvirtd` instance on a remote machine over a secure SSH tunnel. Note: Gentoo enables the `libssh2` support by default.

This flag should only be enabled if there is an explicit need to use `libssh` library or avoid using `libssh2` library.

### libvirtd
Ensure that at least one of the backend flags (`lxc`, `openvz`, `qemu`, `virtualbox` or `xen`) is enabled. Pass the `-Ddriver_libvirtd=enabled` option to the meson build script. Build and install the `libvirtd` daemon that performs required management tasks for virtualized guests. This includes activities such as starting, stopping and migrating guests between host servers, configuring and manipulating networking, and managing storage for use by guests.

This flag can be safely disabled if the daemon is not required.

### lvm
Pass the `-Dstorage_lvm=enabled` and `-Dstorage_mpath=enabled` options to the meson build script. Provide an ability to use virtual machine storage pools based on LVM2 volume groups.

This flag should be enabled if there is a need to use LVM2 volumes for VM storage pool.

### lxc
Ensure that the `libvirtd` and `caps` flags are enabled. Pass the `-Ddriver_lxc=enabled` option to the meson build script. Enable support for managing LXC (Linux Containers) through `livirtd` using direct Kernel features and without requiring LXC userspace tools.

The flag should be enabled if there is a need to manage LXC containers using the `libvirtd` daemon.

### macvtap
Pass the `-Dmacvtap=enabled` option to the meson build script. Enable support for macvtap "direct" connection that allows to connect a virtual machine directly to the physical network without using a host bridge device and providing no restrictions on inbound or outbound connections.

It is safe to disable this flag.

### nfs
Pull in the [net-fs/nfs-utils](../net-fs/nfs-utils.md) package as a dependency. Provide an ability to use the directories exported through NFS (Network filesystem) as a storage pool for virtual machines.

This flag can be safely disabled if there is no need to use NFS shares for VM storage.

### nls
Pass the `-Dnls=enabled` option to the meson build script. Install translation `po` files and use the gettext library to allow translating programs messages into various languages based on the system locale.

It is safe to disable the flag, unless there is a need to use non-English languages.

### numa
Pass the `-Dnumactl=enabled` and `-Dnumad=enabled` options to the meson build script. Ensure that `libvirt` is able to properly handle NUMA (Non-Uniform Memory Access) placement to allow better page allocation and CPU pinning features for managed virtual machines.

This flag should be enabled if the hypervisor host has multiple CPUs, and should be disabled otherwise.

### openvz
Ensure that the `libvirtd` flag is enabled. Pass the `-Ddriver_openvz=enabled` option to the meson build script. Enable the OpenVZ driver that allows to use and manage container based virtualization using OpenVZ Linux container system. This requires OpenVZ-enabled kernel.

This flag should only be enabled if there is a need to run OpenVZ based containers and hypervisor kernel is OpenVZ-enabled.

### parted
Pass the `-Dstorage_disk=enabled` option to the meson build script. Provide an ability to use the physical disk based storage pool for virtual machines. Volumes are created by adding partitions to the disk.

This flag can be safely disabled, unless there is a need to use physical disks as a storage pool.

### pcap
Pass the `-Dlibpcap=enabled` option to the meson build script. Use the `libpcap` library, when applying a traffic filter rule to the interface without an IP address defined, to snoop on network traffic a guest sends, attempt to identify the first IP address it uses and lock traffic to this address.

This flag can be disabled if all guests will be using static IPs, however it is recommended to enabled it if there is a need to use traffic filtering for guests with dynamic IP address allocation, e.g. using the DHCP protocol.

### policykit
Only works together with the `dbus` flag. Pass the `-Dpolkit=enabled` option to the meson build script. Integrate with PolicyKit framework to provide fine grained permission rules across client users, managed objects and API operations using JavaScript rules.

This flag can be safely disabled, but it is recommended to enable it and configure access controls for production usage.

### qemu
Ensure that the `libvirtd` flag is enabled. Pass the `-Ddriver_qemu=enabled` and `-Dyajl=enabled` options to the meson build script. Enable QEMU/KVM hypervisor driver for managing QEMU based guests.

This flag can be safely disabled, unless there is a need to run QEMU based virtual machines.

### rbd
Add the `ceph` dependency to the `libvirtd` init script. Pass the `-Drbd=enabled` option to the meson build script. Enable RBD storage driver that provides a storage pool that stores RBD (RADOS Block Device, part of the Ceph distributed storage project) images in a RADOS pool.

This flag can be safely disabled and only supports the QEMU backend with RBD support.

### sasl
Pass the `-Dsasl=enabled` option to the meson build script. Integrate with the `cyrus-sasl` library to provide a pluggable authentication system using the SASL protocol, which can be used in combination with libvirtd's TLS or TCP socket listeners.

This flag can be safely disabled if there is no need to use SASL protocol (including GSSAPI or Kerberos) authentication.

### selinux
Pass the `-Dselinux=enabled` option to the meson build script. Enable sVirt (Secure Virtualization) plugin that uses SELinux to provide isolation and separation between different virtual machines by preventing different guest from interacting with each other, hypervisor or any of their content.

This flag should be enabled on systems with SELinux-enabled kernel to isolate guests.

### udev
Pass the `-Dudev=enabled` option to the meson build script. Integrate with the Udev device manager to enumerate and manage physical and virtual host devices like PCI, USB, SCSI, network cards, etc and their virtualized capabilities, such as SR-IOV, NPIV, MDEV, DRM and others.

This flag should be enabled if there is a need to provide an access to host devices from guest machines.

### vepa
Pass the `-Dvirtualport=enabled` option to the meson build script. Enable support for the 802.11Qgh (aka VEPA, Virtual Ethernet Port Aggregator) mode of the MacVTap driver. In this mode all packets from a guest machine are forced to be sent through an external switch.

This flag should normally be disabled, unless there is a desire to use VEPA-enabled switches for guest traffic routing.

### virt-network
Ensure that the `libvirtd` flag is enabled. Pass the `-Ddriver_network=enabled` option to the meson build script. Enable the `libvirt`'s virtual networking support, that is using a virtual switch (creating a bridge device on the host machine), provides DHCP and DNS services (by using the `dnsmasq` daemon), and can operate either in the NAT mode (using IPTable masquerade rules to allow external world communication), routed mode (where guest machines can access hosts physical network), or isolated mode (where only communication between guests is allowed, but not with host or external network).

This flag should be enabled if there is a need to use the libvirts virtual networking and can be disabled otherwise.

### virtualbox
Pass the `-Ddriver_vbox=enabled` option to the meson build script. Build and install the VirtualBox hypervisor driver that can manage VirtualBox guest machines. This requires VirtualBox version 4.0 or newer.

This flag can be safely disabled if there is no need to manage VirtualBox guests using libvirt.

### wireshark-plugins
Pass the `-Dwireshark_dissector=enabled` option to the meson build script. Build Wireshark dissector for the Libvirt RPC protocol that provides Libvirt packet overview and their detailed analysis in Wireshark.

This flag should normally be disabled, unless there is a need to intercept and analyze RPC traffic.

### xen
Ensure that the `libvirtd` flag is enabled. Pass the `-Ddriver_libxl=enabled` option to the meson build script. Build and install the Xen hypervisor driver that provides an ability to manage virtual machines on Xen hypervisor of version 4.6.0 or newer.

This flag can be safely disabled, unless there is a need to manage Xen guests using libvirt.

### zfs
Pass the `-Dstorage_zfs=enabled` option to the meson build script. Enable support for ZFS (Z File System) based guest storage pool, and allowing to use manually created `zpool`s, as well as creating ones on-demand.

The flag should normally be disabled, unless there is a desire to use ZFS as a storage pool for virtual machines.
