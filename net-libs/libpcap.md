# net-libs/libpcap

### bluetooth
Pass the `--enable-bluetooth` option to the configure script. Provide an ability to capture Bluetooth communication packets.

This flag can be safely disabled.

### dbus
Pass the `--enable-dbus` option to the configure script. Provide an ability to capture D-Bus communication packets.

It is safe to disable this flag.

### netlink
Pass the `--with-libnl` option to the configure script. Use the `libnl` library to create a `monN` interfaces via the Netlink API when monitor mode for 802.11 (wireless) adapters is requested, which is preferable over the traditional `ioctl` calls. This mode is used by the `tcpdump`, and TShark and dumpcap from the Wireshark distribution.

This flag can be safely disabled, but is recommended when there is a need to run in monitor mode on wireless adapters.

### rdma
Pass the `--enable-rdma` option to the configure script. Enable RDMA (Remote Direct Memory Access) capture module, which exposes RDMA devices under an interface name equal to their `libibverbs` name. The module uses the RDMA verbs interface to create a receive queue with a flow steering rule that
gets a copy of all packets, even offloaded packets generated or consumed by the hardware.

This flag should normally be disabled.

### remote
Pass the `--enable-remote` option to the configure script. Build and install the `rpcapd` daemon that can be used for remote packet capture, i.e. allow remote clients to connect and sniff traffic from the system.

This flag should normally be disabled, especially in production environments, because this greatly increases an attack vector for malicious actors.

### static-libs
This flag does nothing when enabled, and a statically linked version of the `libpcap` library is built and installed into the system. When disabled, the statically linked version will be removed before package is installed.

This flag should be disabled, unless there is a need for the static library.

### usb
Pass the `--enable-usb` option to the configure script. Enable Linux USB capture support that uses the `usbmon` kernel driver to sniff on any communication between the system and USB devices.

It is safe to disable this flag.

### yydebug
Pass the `--enable-yydebug` option to the configure script. Enable debugging mode for the filter expression parser.

This flag should normally be disabled, as this debugging mode is primarily oriented towards the developers.
