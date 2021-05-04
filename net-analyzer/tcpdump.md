# net-analyzer/tcpdump

### drop-root
Pass the `--with-cap-ng`, `--with-chroot=''`, and `--with-user=pcap` options to the configure script. Use the `libcap-ng` library to drop root privileges, keeping only capabilities that are required for proper `tcpdump` operation, set a user to `pcap` when dropping elevated privileges and disable chrooting.

It is recommended to enable this flag to improve security, especially if the `suid` flag is also enabled.

### samba
Pass the `--enable-smb` option to the configure script. Build a fairly extensive SMB/CIFS/NBT packet decoding for data on UDP/137, UDP/138 and TCP/139, as well as some primitive decoding of IPX and NetBEUI SMB data.

This flag should normally be disabled, because this feature considered "possibly buggy".

### smi
Pass the `--with-smi` option to the configure script. Link against the `libsmi` library to provide an ability to load MIB (Management Information Base) modules on the fly at runtime (using the `-m` option) to decode SNMP (Simple Network Management Protocol) packets.

It is safe to disable this flag.

### ssl
Pass the `--with-crypto=/usr` option to the configure script. Use the `OpenSSL` library to perform various cryptographic operations, such as decrypting IKE/ESP (Internet Key Exchange/Encapsulating Security Payload) VPN (Virtual Private Network) traffic using `-E` option, or performing TCP MD5 or HMAC MD5 signature verification using the `-M` option.

This flag can be safely disabled.

### suid
Set the `setuid` bit and the owning group to `pcap` on the `tcpdump` binary, and set the permissions in such a way to restrict execution for owning user (`root`) and group (`pcap`) only. This is done so that users in the `pcap` group can run the `tcpdump` command, without having elevated privileges.

It is recommended to disable this flag, because it poses a security risk.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
