# net-misc/iputils

### arping
Pass the `-DBUILD_ARPING=true` option to the meson build command. This will make sure that `arping` binary is built and installed. This tool allows to ping hosts using ARP protocol. It can be used to detect what IP addresses are already taken on the network.

This flags conflicts with [net-misc/arping](arping.md) package.

### caps
Pass the `-DUSE_CAP=true` option to the meson build command and enable support for Linux capabilities. This allows programs like `ping`, `arping` and others to drop capabilities they don't require for proper operation. This is a security feature.

It is a good idea to enable this flag to ensure that aforementioned binaries only keep relevant capabilities.

### clockdiff
Pass the `-DBUILD_CLOCKDIFF=true` option to the meson build command. Build and install `clockdiff` binary. This tool measures a difference between host it is running on and destination using ICMP protocol.

No packages in portage depend on this flag and it is safe to disable.

### doc
Pass the `-DBUILD_HTML_MANS=true` option to the meson build command. Build and install manual pages in the HTML format.

This flag can be enabled if there is a need for user facing documentation in the HTML format (similar to what manpages provide).

### filecaps
Set the `CAP_NET_RAW` capability on `ping`, `arping` and `clockdiff` binaries. Doing so will allow regular users to execute these commands. Otherwise elevated permissions will be required to run them.

It is recommended to enable this flag so regular (non-root) users can use aforementioned tools.

### idn
Pass the `-DUSE_IDN=true` option to the meson build command. Use the `libidn2` library to enable support for IDN (Internationalized Domain Names), i.e. domain names written using non-latin scripts.

This flag can be safely disabled if there is no need to deal with non-English domain names.

### nls
Pass the `-DUSE_GETTEXT=true` option to the meson build command. Use the gettext library to provide localization support, e.g. display output in a native language based on the system locale, instead of using English.

It is safe to disable the flag, unless there is a need to use a non-English language.

### rarpd
Pass the `-DBUILD_RARPD=true` option to the meson build script. Build and install the `rarpd` daemon binary and init scripts (no support for SystemD services at this time). This daemon is necessary to respond to RARP (Reverse Address Resolution Protocol) requests.

RARP is an older alternative to DHCP and is not recommended nowadays, so it is safe to disable this flag unless non-PXE network booting for specific devices is necessary.

### rdisc
Pass the `-DBUILD_RDISC=true` and `-DENABLE_RDISC_SERVER=true` options to the meson build command. Build and install the `rdisc` binary - a tool that implements both a client and a server side parts of the ICMP router discovery protocol, allowing a system to ask for and accept routing tables from routers, as well as respond to queries.

This flag is only necessary if system to be part of RDISC capable network(s). Otherwise it is completely safe to disable.

### static
This flag will append `-static` option to `LDFLAGS` for building statically linked binaries.

It is recommended to disable this flag for regular system.

### test
Pass the `-DSKIP_TESTS=false` (`true` if the flag is disabled) option to the Meson build script. Execute the `meson test` command after the main build is completed to run the test suite provided with the source code and check for any regressions.

This flag should normally be disabled, because these tests are mainly used by the maintainers, testers and developers.

### tftpd
Pass the `-DBUILD_TFTPD=true` option to the meson build commmand. Build and install the `tftpd` server component for TFTP (Trivial File Transfer Protocol) support, that is most commonly used for network boot (PXE).

This flag can safely be disabled unless TFTP server is required (e.g. to run PXE booting server or flashing firmware into certain routers).

### tracepath
Pass the `-DBUILD_TRACEPATH=true` option to the meson build commmand. Build and install the `tracepath` tool. If `ipv6` flag is also enabled tracepath will be built with IPv6 protocol support and the `tracepath6` compatibility link will be created.

This flag can safely be disabled if `tracepath` tool is not required (e.g. for network diagnostics/debugging).

### traceroute6
Only works if the `ipv6` flag is enabled. Pass the `-DBUILD_TRACEROUTE6=true` option to the meson build command. Build and install the `traceroute6` tool. This flag conflicts with [net-analyzer/traceroute](../../net-analyzer/traceroute.md).

This flag is not recommended because it only installs IPv6 protocol oriented tool and does not work for IPv4 protocol. It is necessary to install `traceroute` via standalone package if IPv4 protocol support is desired.
