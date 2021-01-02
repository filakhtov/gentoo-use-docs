# net-firewall/iptables

### conntrack
Patch the `configure` script to hardcode the `nfconntrack=1` variable (`0` if the flag is disabled) to avoid "automagic" `libnetfilter_conntrack` dependency. Build the `connlabel` module that can be used at runtime using the `-m connlabel` option to attach up to 128 unique bit-based labels to the connection.

This flag can be safely disabled.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable support for the IPv6 protocol. Install appropriate tools, such as `ip6tables`, `ip6tables-save`, `ip6tables-restore` and relevant include files, i.e. `ip6tables.h`. Also install startup scripts to store rules on shutdown and restore them at boot times, both for OpenRC and systemd init systems.

It is safe to disable this flag, however it is necessary to enable it if there is a need to configure firewall rules for the IPv6 protocol.

### netlink
Patch the `configure` script to hardcode the `nfnetlink=1` variable (`0` if the flag is disabled) to avoid "automagic" `libnfnetlink` dependency. Build the `nfnl_osf` module that can perform passive operating system fingerprinting, based on window size, MSS, options and their order obtained from packets with SYN bit set.

This flag should normally be disabled.

### nftables
Pass the `--enable-nftables` option to the configure script. Enable compatibility layer for nftables. Build and install a bunch of tools, such as `iptables-nft`, `iptables-nft-restore`, `iptables-nft-save`, `iptables-translate` (and their IPv6 variants if the appropriate flag is enabled) that help to parse the iptables syntax and translate it to the appropriate nftables commands, pack them into the netlink messages and submit to the kernel.

It is safe to disable this flag and it is only necessary if there is a need to use iptables syntax with nftables.

### pcap
Pass the `--enable-bpf-compiler` and `--enable-nfsynproxy` options to the configure script. Build and installe the `nfbpf_compile` utility that aids in generating BPF byte code suitable for passing to the iptables bpf match, and the `nfsynproxy` tool that is used to detect parameters for the SYNPROXY module. These utilities are useful for advanced packet capture and inspection.

This flag should normally be disabled.

### split-usr
Install dynamic libraries that are required for iptables utilities to properly operate into the `/lib64` (or `/lib32` for 32-bit OS) directory, instead of their usual `/usr/lib64` (or `/usr/lib32`) directory. This is necessary if the system uses a separate `/usr` partition, so that these tools can be executed during the early boot.

This flag should be enabled on the systems that have a separate partition for the `/usr` directory.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of various libraries provided by iptables, such as `libxtables`, `libip4tc`, `libip6tc` and so forth.

This flag should only be enabled if there is a need for statically linked libraries.
