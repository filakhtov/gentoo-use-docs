# sys-apps/tcp-wrappers

### ipv6
Append the `-DINET6=1 -Dss_family=__ss_family -Dss_len=__ss_len` options to the `COPTS` variable passed to the make command. Enable support for the connections coming via the IPv6 protocol.

This flag should only be enabled if the target system participates in an IPv6-capable network.

### netgroups
Pass the `-DNETGROUPS` option to the `NETGROUP` variable and the `-lnsl` option to the `LIBS` variable passed to the make command. Provide support for netgroups in the `hosts.allow` and `hosts.deny` configuration files via the `@` character to enabled permission checking via, for example, NIS or LDAP.

This flag should only be enabled if there is a need for netgroups support.

### static-libs
Pass the `libwrap.a` option to the `LIB` variable passed to the make command. Build and install a statically linked version of the `libwrap` library.

This flag should only be enabled if there is a need for the static library.
