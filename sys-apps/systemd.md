# sys-apps/systemd

### acl
Enabling this flag will pass the `-Dacl=true` to the Meson build script. This in turn will enable support for the ACL permission mechanism for various tools. If enabled, a `journald`, for example, checks ACLs in addition to regular permissions on journal files before accessing them and a `systemd-nspawn` updates ACL entries when the `--private-users-chown` option is used.

It is recommended to enable this flag if an ACL is enabled in any other parts of the system. On modern systems ACLs are usually set on `/dev/dri/*` devices to grant unprivileged users access to the GPU acceleration.

### apparmor
Enabling this flag will pass the `-Dapparmor=true` to the Meson build script. This allows systemd and all its subsystems to properly operate under the AppArmor security framework restrictions by applying appropriate profiles.

This flag must be enabled if systemd will run on an AppArmor-enabled kernel, otherwise it is not recommended.

### audit
Enabling this flag will pass the `-Daudit=true` to the Meson build script. This enables the auditing support for logging to the Linux Auditing System and can be useful for debugging SELinux or AppArmor profiles.

This flag is safe to disable.

### build
This flag is used by the Gentoo team during early build stages for creating build images and bootstrapping. Under the hood it ignores dependency on the `kill` binary provided by one of [sys-apps/util-linux](util-linux.md), [sys-process/procps](../sys-process/procps.md) or [sys-apps/coreutils](coreutils.md) package.

This flag should normally be disabled.

### cgroup-hybrid
When enabled, pass the `-Ddefault-hierarchy=hybrid` option to the Meson build script. This will enable the hybrid cgroup tree setup, where v1 cgroups are mounted under the `/sys/fs/cgroup/<controller>` directories and the v2 cgroup tree is mounted under the `/sys/fs/cgroup/unified`. If disabled, the `-Ddefault-hierarchy=unified` option will be passed instead and only v2 cgroups will be mounted.

It is preferable to disable this flag on the modern system that require no support for v1 cgroups.

### cryptsetup
Passes the `-Dlibcryptsetup=true` to the Meson build script enabling support for encrypted file-systems. This will build and install a set of binaries to deal with `cryptsetup` partitions and associated `.service` files.

The `systemd-cryptsetup-generator` is provided to automatically convert `/etc/crypttab` into systemd service files on boot.

This flag is recommended if support for encrypted partitions using the cryptsetup is necessary.

### curl
This flag passes the `-Dlibcurl=true` option to the Meson build script. cURL dependency is necessary for a systemd remote journal uploading via the `systemd-journal-upload` and for downloading machine images using the `systemd-importd`.

This flag can be safely disabled if an `importd` functionality is not desired.

### dns-over-tls
Pass the `-Ddns-over-tls=true` to the Meson build script. Enable DoT (DNS over TLS) support for systemd via the `systemd-resolved` service to wrap DNS queries and answers via the TLS (Transport Layer Security) protocol in order to prevent eavesdropping and manipulation of DNS data via MITM (man-in-the-middle) attacks.

It is recommended to enable this flag if the system uses a DNS server that supports encrypted connections to improve privacy.

### elfutils
This flag is passing the `-Delfutils=true` option to the Meson build script. Resulting systemd binaries will be linked against the `libdw` library (from a [dev-libs/elfutils](../dev-libs/elfutils.md) package) to allow them to obtain and include stack traces into the coredump files processed by the `systemd-coredump` during a crash handling routine and when saving Kernel pstore using the `systemd-pstore`.

This flag should normally be disabled, and can be enabled for debugging purposes, when there is a need to obtain stack traces.

### gcrypt
Passes the `-Dgcrypt=true` to the Meson build script. This flag enables support for the `allow-downgrade` mode of a DNSSEC operation for the `systemd-resolved`. It also enables the FSS (Forward Secure Sealing) feature of the `systemd-journald`.

It is safe to disable the flag, unless there is a need to seal a journal or support the DNSSEC downgrading mode.

### gnuefi
This flag passes the `-Dgnu-efi=true` option to the Meson build script and enables compilation and installation of a `systemd-boot` - a systemd EFI boot manager. The `systemd-boot` can be used as a lightweight replacement for a GRUB bootloader on systems that support the UEFI.

This flag should be enabled on UEFI systems to use the `systemd-boot` bootloader.

### homed
Pass the `-Dhomed=true` option to the Meson build script. Build and install the `systemd-homed` daemon, associated service and the `homectl` utility, that can be used to create, remove or inspect home areas, such as directories and network mounts. It supports LUKS2-encrypted per-user partitions (possibly on removable media) and `fscrypt` encrypted directories, as well as `btrfs` per-user subvolumes without encryption, regular directories, or Windows share (CIFS) volumes.

It is safe to disable this flag.

### http
Passes the `-Dmicrohttpd=true` option to the Meson build script. This builds and installs a `systemd-remote-journal` - a server (receiving) part of a remote journalling support. A `ssl` flag has to be enabled too in order to support an HTTPS protocol.

This flag is only required if there is a need for a remote journal collection on the target system.

### hwdb
Pass the `-Dhwdb=true` option to the Meson build script. Build and install the `systemd-hwdb` hardware database management utility that can be used to query and update information in the binary hwdb database, and the `systemd-hwdb-update.service` that will run and add new `.hwdb` entries from the `/etc/udev/hwdb.d` directories into the binary database.

It is recommended to enable this flag.

### idn
This flag passes the `-Dlibidn=true` option to the Meson build script. Enabling it will build the `systemd-networkd` and the `systemd-resolved` daemons with the IDN support using the `libidn2` library.

This flag can be safely disabled if there is no need to deal with non-English domain names.

### importd
Passes the `-Dimportd=true`, the `-Dbzip2=true` and the `-Dzlib=true` options to the Meson build script. It will build and install a `systemd-importd` daemon - a tool for importing, exporting and downloading additional system images for running them as local containers.

The flag can be safely disabled if there is no need to run containerized environment or managing system images.

### kmod
The flag passes `-Dkmod=true` option to the Meson build script. This will build and install a `systemd-modules-load` - a tool responsible for loading kernel modules during a boot process.

It is recommended to keep this flag enabled. However, it can be safely disabled if a target system kernel is compiled with all modules built-in.

### lz4
The flag passes `-Dlz4=true` option to the Meson build script. Enable LZ4 algorithm support that can be used for compressing journal files by the `journald`.

The flag can be disabled if no journal compression is required.

### lzma
This flag passes `-Dxz=true` option to the Meson build scrpit. XZ algorithm can be used by the `journald` to compress journal files.

The flag can be disabled if no compression for journal files is desired.

### nat
This flag will pass `-Dlibiptc=true` to the Meson build script. Doing so provides support of netfilter for number of tools.

The `nspawn`, for example, will support the `--port` option. Enabling this flag together with the `kmod` flag will ensure that the `ip_tables` Kernel module is automatically loaded on boot. The `networkd` daemon will gain support for the `IPMasquerade` and the `IPForward` options.

This flag can be safely disabled unless one or more features described above are required.

### pam
The flag will pass `-Dpam=true` option to the Meson build script. This will install the `systemd-user-sessions` binary and the associated `.service` file. It will also install the PAM module for systemd (`pam_systemd.so`) for integrating with `systemd-logind` and registering the user session with systemd control group hierarchy. The module also applies various resource management and runtime parameters to the new session, as configured in the JSON User Record of the user, when one is defined.

This flag is recommended for systems that use the PAM (Pluggable Authentication Module) stack or a graphical desktop environment.

### pcre
This flag passes `-Dpcre2=true` option to the Meson build script. Enable the `-g` and the `--case-sensitive=` options support for `journalctl`, allowing to search for journal entries using PCRE expressions.

This flag can be safely disabled if no pattern matching is required for `journalctl`.

### pkcs11
Pass the `-Dp11kit=true` option to the Meson build script. Enable support for PKCS#11 cryptographic API in the `systemd-homed` and `systemd-cryptsetup` utilities and provide an ability to use hardware security modules (HSM), smart cards and USB keys to obtain cryptographic tokens for decrypting encrypted partitions.

It is safe to disable this flag.

### policykit
Passes the `-Dpolkit=true` option to the Meson build script. The flag enables the Polkit support. It provides an ability to ask for elevated permissions via the Polkit framework for various tools, e.g. `hostnamectl`, `localectl`, `timedatectl`, etc.

This flag is recommended for systems with a graphical desktop environment.

### pwquality
Pass the `-Dpwquality=true` option to the Meson build script. Use the `libpwquality` library and provide the `homectl` and `systemd-homed` utilities with an ability to check for password quality, its strength and against the common passwords list.

This flag should be enabled to improve password security for system users.

### qrcode
The flag passes the `-Dqrencode=true` option to the Meson build script. It will enable an ability to generate a QR-code during FSS configuration using `journalctl` to simplify verification keys transfer.

This flag can be safely disabled, because verification keys can simply be typed or copied away.

# repart
Pass the `-Drepart=true` option to the Meson build script. Build and install the `systemd-repart` tool that can be used to grow and add partitions to a partition table, based on the configuration files described in `repart.d`.

It is safe to disable this flag.

### resolvconf
The resolvectl/systemd-resolve tool provides `resolvconf` compatibility mode. Enabling this flag will install symlink under the `resolvconf` name, in which case it will take arguments and input compatible with the Debian and FreeBSD resolvconf tool.

This flag can be enabled to support resolvconf compatibility mode.

### seccomp
Passes the `-Dseccomp=true` option to the Meson build script. This builds variety of the systemd tools with the `seccomp` filtering framework support. A Kernel has to be compiled with the `seccomp` support for this feature to work properly.

It is a security feature and should generally be enabled.

### selinux
This flag passes the `-Dselinux=true` option to the Meson build script. Doing so will ensure that resulting binaries can properly operate with the SELinux enabled.

For example, various systemd daemons will try to load SELinux policies and check/report permissions denial, they will also manage appropriate xattr labels for various files and the `nspawn-mount` will provide the `/sys/fs/selinux` mount inside of containers.

The flag can only be enabled as a part of the Gentoo `selinux` profile.

### split-usr
The flag will change an installation prefix for the systemd from the default `/usr` location to the `/`. This is only necessary if the system has the separate `/usr` partition, because it requires mounting a device that might not be available during early boot stages.

The flag should not be enabled if the system has the `/usr` directory located on the same partition as `/`.

### static-libs
Pass the `-Dstatic-libsystemd=true` and `-Dstatic-libudev=true` options to the Meson build script. Build a statically linked version of the `libsystemd` and `libudev` libraries.

This flag should only ever be enabled if there is an explicit need for these static libraries.

### sysv-utils
The flag controls whether commands like `halt`, `init`, `poweroff` that are necessary for the SysV compatibility are symlinked to various systemd tools.

It is recommended to enable the flag. A system built with this flag disabled will need to provide the aforementioned tools via the [sys-apps/sysvinit](sysvinit.md) package that isn't aware of the systemd, might cause various compatibility issues and results in additional dependency being installed.

### test
Passes the `-Ddbus=true` option to the Meson build script that is only necessary for running tests. The flag will execute a test suite that is provided with the source code. This will increase the build time.

This flag should only be used for testing and is not recommended for regular system.

### vanilla
This flag will skip applying Gentoo-specific pathces to the systemd source. It will also ignore the [sys-apps/gentoo-systemd-integration](gentoo-systemd-integration.md) dependency.

This flag should normally be disabled.

### xkb
The flag passes the `-Dxkbcommon=true` option to the Meson build script. If enabled, the `localed` daemon will be able to change a keyboard layout for the Xorg server via the X Keyboard Extension (aka XKB). Executing the `localectl set-keymap` command will not only change a console input but also a graphical interface input as well.

This flag is recommended for desktop systems with a desktop environment.

### zstd
Pass the `-Dzstd=true` option to the Meson build script. Provide an ability to compress journald files when writing and decompress them when reading using the zstd (Zstandard) compression algorithm, and allow `systemd-coredump` to compress core dump files using zstd.

It is safe to disable this flag.
