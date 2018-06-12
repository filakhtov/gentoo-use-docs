# sys-apps/systemd
### acl
Enabling this flag will pass the `-Dacl=true` to the Meson build script. This in turn will enable support for the ACL permission mechanism for various tools. If enabled, a `journald`, for example, checks ACLs in addition to regular permissions on journal files before accessing them and a `systemd-nspawn` updates ACL entries when the `--private-users-chown` option is used.

It is recommended to enable this flag if an ACL is enabled in any other parts of the system. On modern systems ACLs are usually set on `/dev/dri/*` devices to grant unprivileged users access to the GPU acceleration.

### apparmor
Enabling this flag will pass the `-Dapparmor=true` to the Meson build script. This allows SystemD and all its subsystems to properly operate under the AppArmor security framework restrictions by applying appropriate profiles.

This flag must be enabled if SystemD will run on an AppArmor-enabled kernel, otherwise it is not recommended.

### audit
Enabling this flag will pass the `-Daudit=true` to the Meson build script. This enables the auditing support for logging to the Linux Auditing System and can be useful for debugging SELinux or AppArmor profiles.

This flag is safe to disable.

### build
This flag is used by the Gentoo team during early build stages for creating build images and bootstrapping. Under the hood it ignores dependency on the `kill` binary provided by one of [sys-apps/util-linux](util-linux.md), [sys-process/procps](../sys-process/procps.md) or [sys-apps/coreutils](coreutils.md) package.

This flag should normally be disabled.

### cryptsetup
Passes the `-Dlibcryptsetup=true` to the Meson build script enabling support for encrypted file-systems. This will build and install a set of binaries to deal with `cryptsetup` partitions and associated `.service` files.

The `systemd-cryptsetup-generator` is provided to automatically convert `/etc/crypttab` into SystemD service files on boot.

This flag is recommended if support for encrypted partitions using the cryptsetup is necessary.

### curl
This flag passes the `-Dlibcurl=true` option to the Meson build script. cURL dependency is necessary for a SystemD remote journal uploading via the `systemd-journal-upload` and for downloading machine images using the `systemd-importd`.

This flag can be safely disabled if an `importd` functionality is not desired.

### elfutils
This flag is passing the `-Delfutils=true` option to the Meson build script. Resulting SystemD binaries will be linked against the `libdw` library (from a [dev-libs/elfutils](../dev-libs/elfutils.md) package) to allow them to obtain and include stack traces into the coredump files generated during a crash handling routine.

### gcrypt
Passes the `-Dgcrypt=true` to the Meson build script. This flag enables support for the `allow-downgrade` mode of a DNSSEC operation for the `systemd-resolved`. It also enables the FSS (Forward Secure Sealing) feature of the `systemd-journald`.

### gnuefi
This flag passes the `-Dgnu-efi=true` option to the Meson build script and enables compilation and installation of a `systemd-boot` - a SystemD EFI boot manager. The `systemd-boot` can be used as a lightweight replacement for a GRUB bootloader on systems that support the UEFI.

### http
Passes the `-Dmicrohttpd=true` option to the Meson build script. This builds and installs a `systemd-remote-journal` - a server (receiving) part of a remote journalling support. A `ssl` flag has to be enabled too in order to support an HTTPS protocol.

This flag is only required if there is a need for a remote journal collection on the target system.

### idn
This flag passes the `-Dlibidn=true` option to the Meson build script. Enabling it will build the `systemd-networkd` and the `systemd-resolved` daemons with the IDN support.

This flag can be safely disabled if there is no need to deal with non-English domain names.

### importd
Passes the `-Dimportd=true`, the `-Dbzip2=true` and the `-Dzlib=true` options to the Meson build script. It will build and install a `systemd-importd` daemon - a tool for importing, exporting and downloading additional system images for running them as local containers.

The flag can be safely disabled if there is no need to run containerized environment or managing system images.

### kmod
The flag passes `-Dkmod=true` option to the Meson build script. This will build and install a `systemd-modules-load` - a tool responsible for loading kernel modules during a boot process.

It is recommended to keep this flag enabled. However, it can be safely disabled if a target system kernel is compiled with all modules built-in.

### libidn2
This flag is not useful on its own but has to be used in conjunction with the `idn` flag. When enabled it passes the `-Dlibidn2=true` option to Meson build script that instructs the build to use newer (second) version of `libidn` that implements the IDNA2008 standard which is incompatible with IDNA2003 provided by older (first) version of `libidn`.

This flag is recomended if the IDN support is desired, unless there is a specific need to support older IDNA2003 standard.

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
The flag will pass `-Dpam=true` option to the Meson build script. This will install the `systemd-user-sessions` binary and the associated `.service` file. It will also install the PAM module for SystemD (`pam_systemd.so`) for integrating with `systemd-logind`.

This flag is recommended for systems with a graphical desktop environment.

### pcre
This flag passes `-Dpcre2=true` option to the Meson build script. Enable the `-g` and the `--case-sensitive=` options support for `journalctl`, allowing to search for journal entries using PCRE expressions.

This flag can be safely disabled if no pattern matching is required for `journalctl`.

### policykit
Passes the `-Dpolkit=true` option to the Meson build script. The flag enables the Polkit support. It provides an ability to ask for elevated permissions via the Polkit framework for various tools, e.g. `hostnamectl`, `localectl`, `timedatectl`, etc.

This flag is recommended for systems with a graphical desktop environment.

### qrcode
The flag passes the `-Dqrencode=true` option to the Meson build script. It will enable an ability to generate a QR-code during FSS configuration using `journalctl` to simplify verification keys transfer.

This flag can be safely disabled, because verification keys can simply be typed or copied away.

### seccomp
Passes the `-Dseccomp=true` option to the Meson build script. This builds variety of the SystemD tools with the `seccomp` filtering framework support. A Kernel has to be compiled with the `seccomp` support for this feature to work properly.

It is a security feature and should generally be enabled.

### selinux
This flag passes the `-Dselinux=true` option to the Meson build script. Doing so will ensure that resulting binaries can properly operate with the SELinux enabled.

For example, various SystemD daemons will try to load SELinux policies and check/report permissions denial, they will also manage appropriate xattr labels for various files and the `nspawn-mount` will provide the `/sys/fs/selinux` mount inside of containers.

The flag can only be enabled as a part of the Gentoo `selinux` profile.

### split-usr
The flag will change an installation prefix for the SystemD from the default `/usr` location to the `/`. This is only necessary if the system has the separate `/usr` partition, because it requires mounting a device that might not be available during early boot stages.

The flag should not be enabled if the system has the `/usr` directory located on the same partition as `/`.

### ssl
The flag will pass the `-Dgnutls=true` option to the Meson build script, but only if the `http` flag is also enabled. The GnuTLS will be used by the `systemd-journal-remote` to support HTTPS protocol.

The flag should not be enabled on its own and should only be used for the remote journalling where incoming connections are made over the Sercure HTTP (HTTPS) protocol.

### sysv-utils
The flag controls whether commands like `halt`, `init`, `poweroff` that are necessary for the SysV compatibility are symlinked to various SystemD tools.

It is recommended to enable the flag. A system built with this flag disabled will need to provide the aforementioned tools via the [sys-apps/sysvinit](sysvinit.md) package that isn't aware of the SystemD, might cause various compatibility issues and results in additional dependency being installed.

### test
Passes the `-Ddbus=true` option to the Meson build script that is only necessary for running tests. The flag will execute a test suite that is provided with the source code. This will increase the build time.

This flag should only be used for testing and is not recommended for regular system.

### vanilla
This flag will skip applying Gentoo-specific pathces to the SystemD source. It will also ignore the [sys-apps/gentoo-systemd-integration](gentoo-systemd-integration.md) dependency.

This flag should normally be disabled.

### xkb
The flag passes the `-Dxkbcommon=true` option to the Meson build script. If enabled, the `localed` daemon will be able to change a keyboard layout for the Xorg server via the X Keyboard Extension (aka XKB). Executing the `localectl set-keymap` command will not only change a console input but also a graphical interface input as well.

This flag is recommended for desktop systems with a desktop environment.
