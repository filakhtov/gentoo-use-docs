# net-misc/iputils
### arping
Enabling this flag will make sure that `arping` binary is built and installed. This tool allows to ping hosts using ARP protocol. It can be used to detect what IP addresses are already taken on the network.

This flags conflicts with [net-misc/arping](arping.md) package.

### caps
Pass `USE_CAP=yes` to `make` invocation and thus enable support for Linux capabilities. This allows programs like `ping`, `arping` and others to drop capabilities they don't require for proper operation. This is a security feature.

### clockdiff
Build and install `clockdiff` binary. This tool measures a difference between host it is running on and destination using ICMP protocol.

No packages in portage depend on this flag and it is safe to disable.

### doc
This will execute `make html` that builds and installs documentation in HTML format.

### filecaps
Set `CAP_NET_RAW` capability on `ping`, `arping` and `clockdiff` binaries. Doing so will allow regular users to execute these commands. Otherwise elevated permissions will be required to run them.

### gcrypt
Use `gcrypt` for Encryption and Authentication features of IPv6 stack for `ping6` tool. This flag does not make any changes if `ipv6` or `ssl` flags are disabled.

This flag conflicts with `openssl`, `libressl` and `nettle`, because only one SSL backend can be used at a time.

### idn
Pass `USE_IDN=yes` to `make` invocation and thus enable support for Internationalized Domain Names (i.e. domain names written in languages other than English).

This flag can be safely disabled if there is no need to deal with non-English domain names.

### ipv6
Pass `IPV4_DEFAULT=no` to `make` invocation. Enable IPv6 protocol support in tools that can use it (e.g. `tracepath`). Also enable building and installing additional tools that support IPv6 protocol (e.g. `ping6`).

This flag is recommended if target system is to be participating in IPv6 capable network(s), otherwise it can safely be disabled.

### libressl
Use `libressl` for Encryption and Authentication features of IPv6 stack for `ping6` tool. This flag does not make any changes if `ipv6` or `ssl` flags are disabled.

This flag conflicts with `openssl`, `nettle` and `gcrypt`, because only one SSL backend can be used at a time.

### nettle
Use `nettle` for Encryption and Authentication features of IPv6 stack for `ping6` tool. This flag does not make any changes if `ipv6` or `ssl` flags are disabled.

This flag conflicts with `openssl`, `libressl` and `gcrypt`, because only one SSL backend can be used at a time.

### openssl
Use `openssl` for Encryption and Authentication features of IPv6 stack for `ping6` tool. This flag does not make any changes if `ipv6` or `ssl` flags are disabled.

This flag conflicts with `nettle`, `libressl` and `gcrypt`, because only one SSL backend can be used at a time.

### rarpd
Install `rarpd` daemon binary and init scripts (no support for SystemD services at this time). This daemon is necessary to respond to RARP (Reverse Address Resolution Protocol) requests.

RARP is an older alternative to DHCP and is not recommended nowadays, so it is safe to disable this flag unless non-PXE network booting for specific devices is necessary.

### rdisc
This flag enables `rdisc` binary installation, a tool that implements client side part of ICMP router discovery protocol, allowing system to ask for and accept routing tables from routers.

This flag is only necessary if system to be part of RDISC capable network(s). Otherwise it is completely safe to disable.

### SECURITY_HAZARD
Enabling this flag will apply patch that allows unprivileged users to use flood ping. As flag name indicates this is a security problem, especially on multi-user systems with untrusted access.

This flag should normally be disabled.

### ssl
Enable Encryption and Authentication features of IPv6 protocol for `ping6` tool. This flag does not make any changes if `ipv6` flag is disabled.

Enabling this flag will require to enable one of the available SSL backends: `openssl`, `gcrypt`, `nettle` or `libressl`.

If `ping6` tool returns a following message:

> ping6: function not available; crypto disabled

for some or all hosts, it means that `ssl` flag must be enabled in order to make it work.

### static
This flag will append `-static` option to `LDFLAGS` for building statically linked binaries.

It is recommended to disable this flag for regular system.

### tftpd
Enable `tftpd` server installation for TFTP (Trivial File Transfer Protocol) support.

This flag can safely be disabled unless TFTP server is required (e.g. to run PXE booting server or flashing firmware into certain routers).

### tracepath
Enable `tracepath` tool installation. If `ipv6` flag is also enabled tracepath will be built with IPv6 protocol support.

This flag can safely be disabled if `tracepath` tool is not required (e.g. for network diagnostics/debugging).

### traceroute
Enable `traceroute6` tool installation. This flag does not make any changes if `ipv6` flag is disabled. This flag conflicts with [net-analyzer/traceroute](../../net-analyzer/traceroute.md).

This flag is not recommended because it only installs IPv6 protocol oriented tool and does not work for IPv4 protocol. It is necessary to install `traceroute` via standalone package if IPv4 protocol support is desired.
