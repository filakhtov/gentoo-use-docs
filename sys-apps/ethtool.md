# sys-apps/ethtool

### netlink
Pass the `--enable-netlink` option to the configure script. Enable support for Netlink based alternative userspace interface for ethtool, that is designed to address long known issues with the ioctl interface, such as lack of extensibility, raciness, limited error reporting and absence of notifications.

It is recommended to enable this flag.
