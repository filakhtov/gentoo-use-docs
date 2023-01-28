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

### test
Pass the `-DSKIP_TESTS=false` (`true` if the flag is disabled) option to the Meson build script. Execute the `meson test` command after the main build is completed to run the test suite provided with the source code and check for any regressions.

This flag should normally be disabled, because these tests are mainly used by the maintainers, testers and developers.

### tracepath
Pass the `-DBUILD_TRACEPATH=true` option to the meson build commmand. Build and install the `tracepath` tool. If `ipv6` flag is also enabled tracepath will be built with IPv6 protocol support and the `tracepath6` compatibility link will be created.

This flag can safely be disabled if `tracepath` tool is not required (e.g. for network diagnostics/debugging).
