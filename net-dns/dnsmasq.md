# net-dns/dnsmasq

### auth-dns
Provide an ability for dnsmasq to act as an authoritative DNS server for one or more zones, e.g. answering DNS queries directly, instead of delegating them to other authoritative servers. Append the `-DNO_AUTH` option to the `COPTS` variable and pass it to the `make` command when the flag is disabled in order to turn this feature off.

This flag can be safely disabled if there is no need to serve DNS zone from dnsmasq.

### conntrack
Append the `-DHAVE_CONTTRACK` (`-DNO_CONNTRACK` when the flag is disabled) option to the `COPTS` variable that's passed to the `make` command. Enable support for Linux `conntrack` firewall component to provide an ability to preserve `connection marks` of the incoming requests when performing an outgoing request from dnsmasq itself.

It is safe to disable this flag, unless there is a need to handle "marked" connections.

### dbus
Append the `-DHAVE_DBUS` (`-DNO_DBUS` if the flag is disabled) option to the `COPTS` variable that is passed to the `make` command. Enable D-Bus support that provides `uk.org.thekelleys.dnsmasq` service and allows clearing cache, changing upstream DNS servers, adding DHCP leases and so on and also send DHCP-related signals over the D-Bus interface.

This flag can be safely disabled if there is no need to use provide D-Bus service.

### dhcp
Enable support for acting as a DHCP server (including for the IPv6 protocol if the `ipv6` flag is also enabled) to provide an ability to assign IP addresses, default gateway and other network parameters to the devices on the network. Append the `-DNO_DHCP` and `-DNO_DHCP6` option to the `COPTS` variable when the flag is disabled to disable the DHCP support.

It is safe to disable this flag.

### dhcp-tools
Requires the `dhcp` flag to be enabled. Build and install `dhcp_release` (and `dhcp_release6` if the `ipv6` flag is also enabled) tool that allows to release a DHCP lease on the local dnsmasq server, and `dhcp_lease_time` tool that allows querying the remaining lease time from the local dnsmasq server.

This flag can be safely disabled.

### dnssec
Append the `-DHAVE_DNSSEC` option to the `COPTS` variable that is passed to the `make` command. Enable support DNSSEC (Domain Name System Security Extensions) validation and caching when passing through DNS requets. When disabled, append the `-DNO_DNSSEC` option to the `COPTS` variable instead in order to disable support for DNSSEC.

It is safe to disable this flag, unless there is a need to validate DNSSEC data.

### dumpfile
Build additional code to support dumping copies of network packets received and sent to a pcap-format (packet capture) file for further analysis and debugging. When the flag is disabled, pass the `-DNO_DUMPFILE` option to the `COPTS` variable that is passed to the `make` command to disable this dumping code.

This flag should normally be disabled.

### id
Enable support to provide cache statistics in response to CHAOS TXT DNS queries for `*.bind` domains. The supported domain names are `cachesize.bind`, `insertions.bind`, `evictions.bind`, `misses.bind`, `hits.bind`, `auth.bind` and `servers.bind`. If the flag is disabled, pass the `-DNO_ID` option to the `COPTS` variable that is passed to the `make` command and dnsmasq will forward such queries to an upstream server.

It is safe to disable this flag.

### idn
Appen the `-DHAVE_IDN` option to the `COPTS` variable that is passed to the `make` command. Use the `libidn` library to enable support for IDN (internationalized domain name) so that domain names in `/etc/hosts`, `/etc/ethers` and `/etc/dnsmasq.conf` which contain non-ASCII characters will be translated to the DNS-internal punycode representation. This has no difference on forwarded and cached DNS entries. When the flag is disabled, pass the `-DNO_IDN` option to the `COPTS` instead.

This flag should normally be disabled.

### inotify
Use the `inotify` Linux kernel API to be notified about any changes to relevant configuration files and automatically reload them, instead of periodically polling for such changes. Pass the `-DNO_INOTIFY` option to the `COPTS` variable that is passed to the `make` command if the flag is disabled to disable support for monitoring.

It is recommended to enable this flag on any modern Linux kernel.

### ipv6
Enable support for IPv6 protocol, both for DNS and DHCP (if the `dhcp` flag is also enabled). This provides support for DHCPv6, IPv6 RA (Router Advertisement), and `AAAA` DNS entries. When the flag is disabled, pass the `-DNO_IPV6` and `-DNO_DHCP6` options to the `CMAKE` variable that is passed to the `make` command to disable IPv6 capabilities.

This flag should only be enabled if there is a need to support IPv6 protocol.

### libidn2
Requires the `idn` flag to be also enabled. Pass the `-DHAVE_LIBIDN2` option to the `COPTS` variable that is passed to the `make` command. Use the `libidn2` library, instead of `libidn` to handle IDN (internationalized domain name) using the IDNA2008 standard, instead of IDNA2003.

It is safe to disable the flag if there is no need to handle IDN names.

### lua
Requires the `script` flag to be enabled. Append the `-DHAVE_LUASCRIPT` option to the `COPTS` variable that is passed to the `make` command. Enable support for LUA scripting language to execute an arbitrary LUA code when the DHCP lease is created, destroyed or changed. If the flag is disabled, append the `-DNO_LUASCRIPT` option to the `COPTS` variable instead to disable support for LUA scripting.

This flag should normally be disabled.

### nls
Run the `all-i18n` make target to build and `install-i18n` to install when the flag is enabled, instead of `all` and `install` respectively. Enable support for internationalisation, i.e. log messages produced and output from various commands will be in the local language, specified by the system locale, instead of English.

It is safe to disable the flag.

### script
Enable support to run an arbitrary scripts when a new DHCP lease is created or an old one is destroyed, or a TFTP file transfer completes. This allows to maintain external lease database in virtually any imaginable format and storage mechanism. When this flag is disabled the `-DNO_SCRIPT` option will be appended to the `COPTS` variable that is passed to the `make` command in order to disable script support.

This flag should normally be disabled.

### selinux
Pull in the [sec-policy/selinux-dnsmasq](../sec-policy/selinux-dnsmasq.md) package as a dependency that provides a SELinux policy to allow running dnsmasq under the SELinux-restricted kernel.

This flag should only ever be toggled system-wide, i.e. as part of the SELinux enabled Portage profile.

### static
This flag only makes sense if the `dnssec` flag is also enabled. Append the `-DHAVE_DNSSEC_STATIC` option to the `COPTS` variable that is passed to the `make` command. Statically link dnsmasq binaries against `libgmp` and `libnettle` libraries that are required for DNSSEC support.

This flag should normally be disabled.

### tftp
Enable support for dnsmasq's built-in TFTP (Trivial File Transfer Protocol) server that is normally used for network booting, e.g. to run an operating system installer, live system or actual operating system with remote storage over the network. When the flag is disabled, the `-DNO_TFTP` option will be appended to the `COPTS` variable in order to disable this feature.

It is safe to disable this flag.
