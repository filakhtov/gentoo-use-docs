# sys-apps/coreutils

### acl
Pass the `--enable-acl` to the configure script. Allow an `ls` command to display a `+` sign in a permissions column of a long listing format for files and directories that have ACLs set. Enable a `cp` and an `mv` commands to copy ACL permissions when copying a file. Provide an ability to preserve ACL permissions for an `install` command.

It is recommended to toggle this flag system-wide. Disabling it for some packages while it is enabled for others might and will result in lost ACL permissions.

### caps
When disabled, pass the `--disable-libcap` option to the configure script. Does nothing when enabled, because capabilities support is enabled by default. Provide an ability for `ls` to colorize files that have capabilities set. Allow a `cp` and an `mv` commands to preserve capabilities when copying files.

This flag can be safely disabled unless there is a need to deal with files that have capabilities set.

### gmp
Pass the `--with-libgmp` option to the configure script. Provide an ability for a `factor` command to handle "big numbers", i.e. with precision higher than a native processor can handle using a GMP library.

This flag can be safely disabled.

### hostname
Append `hostname` to a list supplied to the `--enable-install-program` (`--enable-no-install-program` if disabled) option that is passed to the configure script. Build and install a `hostname` command that is normally provided by a [sys-apps/net-tools](net-tools.md) package in a Gentoo distribution.

It is safe to disable this flag.

### kill
Append `kill` to a list supplied to the `--enable-install-program` (`--enable-no-install-program` if disabled) option that is passed to the configure script. Build and install a `kill` command that is normally provided by a `sys-process/procps` command in a Gentoo distribution.

The flag can safely be disabled.

### multicall
Pass the `--enable-single-binary` option to the configure script. Build and install a single binary that provides all coreutils commands (that can be accessed using a `--coreutils-prog` runtime option).

This flag should normally disabled unless there is an explicit need for multicall binary.

### nls
Pass the `--enable-nls` option to the configure script. Provide an ability to translate programs messages into a system locale language using gettext library.

It is safe to disable this flag if there is no need for non-English languages.

### openssl
Pass the `--with-openssl` option to the configure script. Use hash functions provided by the OpenSSL library in the tools like `b2sum`, `md5sum`, `sha1sum`, `cksum` and others, instead of using simplified bundled implementations.

This flag can be safely disabled.

### selinux
When disabled, export the `ac_cv_search_setfilecon=no`, `ac_cv_header_selinux_context_h=no`, `ac_cv_header_selinux_flash_h=no` and `ac_cv_header_selinux_selinux_h=no` variables for the configure script. Does nothing when enabled, because SELinux support will be detected by configure by default. Enable an ability to preserve a SELinux context (or set a default one) while performing various operations, e.g. a `cp`, `mv`, `install`, etc.

This flag should only ever be toggled system-wide, i.e. as part of a SELinux-enabled Portage profile.

### split-usr
Move critical binaries from a `/usr/bin` directory into a `/bin` directory and create symlinks back to a `/usr/bin`. This is necessary to support booting a system with a `/usr` directory on a separate partition.

This flag should only be enabled if there is a need to use a separate partition for a `/usr` directory.

### static
Append `-static` option to the `LDFLAGS` variable. Patch `configure` script to set `elf_sys=no` (instead of default `yes`), see [Gentoo Bug #321821](https://bugs.gentoo.org/321821) for details. Build and install statically linked binaries.

This flag should normally be disabled, unless there is an explicit need for static binaries (usually used together with multicall binary).

### test
Execute the `make check` command after the main bulid is completed to run the test suite provided with the source code and check for any regressions. This will extend a build time.

The flag should normally be disabled as it is primarily used by the maintainers, developers or testers.

### vanilla
Skip applying any Gentoo patches.

This flag should be disabled. It might be useful for testing regressions or reporting issues to upstream.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### xattr
Pass the `--enable-xattr` option to the configure script. Provide an ability to preserve eXtended ATTRibutes for a `cp`, an `mv` and other commands.

It is recommended to toggle this flag system-wide. Disabling this flag for some packages while enabing it for others might and will result in lost XATTRs by unaware programs.
