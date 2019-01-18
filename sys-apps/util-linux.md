# sys-apps/util-linux

### build
This flag is used by Gentoo team when building and bootstrapping early stage images. Under the hood this flag will exclude [sys-apps/systemd](systemd.md) from dependencies regardless if `systemd` USE flag is set or not.

This flag should be disabled.

### caps
This passes `--enable-setpriv` option to configure script. This will build and install `setpriv` tool used to run programs with different set of privileges and capabilities.

No packages in Portage tree require `setpriv` and it is safe to disable this flag if there are no plans to use it directly.

### cramfs
This passes `--enable-cramfs` option to configure script. This option is responsible for building and installing `mkfs.cramfs` and `fsck.cramfs` tools that are responsible for dealing with compressed ROM file system.

This flag can be safely disabled, unless there is a need to manage cramfs.

### fdformat
This will pass `--enable-fdformat` option to configure script. This will build and install `fdformat` tool for low level formatting of a floppy disk.

It is safe to disable this flag, except when it is necessary to deal with floppy disks.

### kill
This passes `--enable-kill` option to configure script. This will build and install `kill` tool responsible for terminating a running process.

Multiple packages in Portage tree provide `kill` binary and therefore `kill` flag can't be enabled on more than one of them at a time.

### ncurses
This flag will pass `--with-ncursesw` (if `unicode` flag is set too) or `--with-ncurses` (if `unicode` flag is disabled). If disabled `--without-tinfo` flag will be passed instead.

This flag enables handling terminal output using ncurses library and colorized output for various tools (e.g. green header in `fdisk` or white background for current day in `cal`, etc).

This flag is safe to disable if colored output is not required.

### nls
This passes `--enable-nls` option to configure script. As a result translation files will be processed and installed, allowing various tools to show localized messages and formats.

This flag can be safely disabled if the only language necessary is English.

### pam
This flag tells ebuild to compile and install `runuser` binary and associated configuration files for PAM subsystem: `runuser` and `runuser-l`.

`runuser` command can be used by root user to execute a process using privileges of different user and group. It is similar to `su` command but has slightly lower overhead, because only `session` PAM modules are executed, while `auth` and `account` ones are skipped.

No packages in Portage tree are dependent on `runuser` and therefore this flag can safely be disabled.

### python
Enables `--with-python` option for configure script. This will build and install `pylibmount.so` - a library that contains Python bindings for `libmount`, allowing Python scripts to retrieve and manipulate file-system mounting.

No packages in portage require this flag and it can be safely disabled, unless there is a need to use Python packages or scripts that depend on `libmount` bindings.

### readline
This flag will pass `--with-readline` option to configure script, enabling support for autocompletion, cursor movement and line editing capabilities for various tools (e.g. `fdisk`, `sfdisk`) that have interactive flows.

This flag can be disabled, but it will result degradation of usability in interactive tools.

### selinux
Enable `--with-selinux` option during configure. This will make sure that various tools behave properly with SElinux enabled. This includes access checking and reporting, manipulating contexts, etc.

This flag should only be enabled profile-wide and require support from Kernel.

### slang
Pass `--with-slang` option to configure script resulting in `cfdisk` using window management capabilities of `slang` for terminal output handling instead of `ncurses` library.

This flag results in the same set of capabilities being build for `cfdisk` as does enabling `ncurses`.

It is safe to disable this flag.

### static-libs
This flag passes `--enable-static` option to configure. As a result static libraries will be built and installed.

This flag should only be set if such libraries are required, e.g. for development or as a dependency for other statically linked packages.

### suid
This flag responsible for passing `--enable-makeinstall-chown` and `--enable-makeinstall-setuid` options to configure. Doing so will instruct `make install` to set special permissions for several commands, so that they can be executed by regular users with elevated privileges (e.g. `mount`, `umount`).

It is required if user mounts for unprivileged users is desired.

### systemd
Enable `--with-sytemd` and pass `--with-systemdsystemunitdir` options to configure script. This will extend behavior of various tools to support running from SystemD init system. It will also install `socket`, `service` and `timer` files for SystemD (e.g. `fstrim.timer` for periodic TRIM calls for SSD file-systems).

Enable this flag if system is using [sys-apps/systemd](systemd.md) as init daemon.

### test
This flag will execute built-in test suite by running `make check`. This will extend build time and is not necessary for average user.

### tty-helpers
This flag passes `--enable-mesg`, `--enable-wall` and `--enable-write` options to configure, resulting in `mesg`, `wall` and `write` binaries being built and installed.

It is recommended to keep this flag enabled as some Gentoo scripts are depending on these commands.

### udev
This passes `--with-udev` configure option. This will enable access to udev information for `findmnt` and `lsblk` tools allowing them to gather and display more data about block devices.

It is safe to disable this flag as no packages in Portage are dependent on it. However a requirement to obtain extended information should be considered first, before doing so.

### unicode
This flag passes `--enable-widechar` configure option. If `ncurses` flag is also set `--with-ncursesw` will be used instead of `--with-ncurses`. This flag enables "wide" character set support (aka multibyte, aka UTF-8). Commands like `dmesg`, `more` and others will benefit from this flag.

It can be safely disabled on systems that are only ever deal with English language.
