# sys-apps/iproute2

### atm
Add a `TC_CONFIG_ATM := y` (`n` when disabled) option to the build configuration file `config.mk` file. Build and install `q_atm.so` library that can be used by the `tc` command to apply QoS settings for ATM (Asynchronous transfer mode) network connections.

This flag should normally be disabled, unless there is a need to apply QoS policies to ATM connections.

### berkdb
Add a `HAVE_BERKELEY_DB := y` (`n` if disabled) option to the build configuration file `config.mk` file. Create a `/var/lib/arpd` directory to store an arp cache database. When disabled, `arpd` daemon won't be built and installed.

This flag should normally be disabled as modern Linux kernels are handling ARP cache properly, however it might be useful if there is a need to maintain a local ARP table.

### caps
Add a `HAVE_CAP := y` (`n` when disabled) option to the build configuration file `config.mk`. Enable support for Linux capabilities to provide an ability to drop elevated privileges and retrain only relevant capabilities to improve security, in particular prevent elevated privileges exploitation.

It is recommended to enable this flag to improve security.

### elf
Add a `HAVE_ELF := y` (`n` when disabled) option to the build configuration file `config.mk`. Enable support for the eBPF (extended Berkeley Packet Filter) classifier and actions for the `tc` (traffic control) tool. Link against the `libelf` library for parsing an ELF file to extract the map and bytecode specification generated from a compiler such as llvm that is then pushed into the kernel by `tc`.

This flag should be enabled if there is a need to use `tc` with the eBPF filters.

### iptables
Add a `TC_CONFIG_XT := y` (`n` when disabled) and a `TC_CONFIG_NO_XT := n` (`y` if disabled) options to the build configuration file `config.mk`. Provide support for xtables based targets for a QoS policing with a `tc` tool.

This flag can be safely disabled.

### ipv6
IPv6 protocol support is enabled by default, so nothing is done when this flag is enabled. If disabled, apply a patch to disable the IPv6 support.

It is recommended to enable this flag if the target system to be participating in IPv6-capable network. Otherwise it can be safely disabled.

### minimal
Patch a `Makefile` to build only a `tc`, `lib` and `ip` directories. Add a `HAVE_MNL := n` and a `HAVE_ELF := n` options (both with `y` value when flag is disabled) to the build configuration file `config.mk`. This will only build and install a `tc` and an `ip` commands without eBPF (extended Berkeley Packet Filter) support. A `bridge`, `genl`, `tipc`, `devlink` and `rdma` commands won't be available. Man pages also won't be built and installed.

This flag should normally be disabled, however it can be useful for embedded systems.

### selinux
Add a `HAVE_SELINUX := y` (`n` when disabled) option to the build configuration file `config.mk` file. Enable SELinux support for an `ss` tool. Provide a `-Z` runtime option.

This flag should only be ever toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.
