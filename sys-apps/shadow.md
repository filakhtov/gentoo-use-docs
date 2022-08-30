# sys-apps/shadow

### acl
Pass the `--with-acl` option to the configure script. Enable ACL support for the `useradd` and `usermod` commands. Copy ACL permissions when creating user home directory from skeleton files via `useradd` (`-m` option) and when moving home directory via `usermod` (`-m` option).

This flag should be toggled system-wide, otherwise there is a high probability of losing important ACLs.

### audit
Pass the `--with-audit` option to the configure script. Add logging support via the Kernel Audit Subsystem using a `libaudit` library for a `useradd`, `groupadd`, `userdel`, `groupdel`, `gpasswd` and other users and groups manipulation commands.

This flag can be safely enabled.

### bcrypt
Pass the `--with-bcrypt` option to the configure script. Provide an ability to use `bcrypt` hashing function for storing passwords, instead of a SHA-based one. The `bcrypt` password-hashing algorithm derived from Bruce Schneier's Blowfish block cipher, which takes advantage of the slow Blowfish key schedule to make password-checking inherently CPU-intensive, so that password-cracking attempts are slower and more difficult.

It is recommended to enable this flag to greatly improve stored password hashes resistance to brute-force and rainbow attacks.

### cracklib
Pass the `--with-libcrack` option to the configure script. Use a `libcrack` library when creating or changing a password for a user or a group using `passwd` command to verify password requirements, such as complexity, blacklist dictionary check and others.

It is safe to disable this flag, however it can add an additional layer of security for the multi-user system.

### nls
Pass the `--enable-nls` option to the configure script. Provide a localization support using gettext. Programs messages and prompts can be translated into system locale and be displayed in various languages.

This flag can be safely disabled, unless there is a need for non-English languages.

### pam
Pass the `--with-libpam` option to the configure script. When disabled, install a `login.access` and a `limits` configuration files into `/etc` directory (normally provided by PAM), also disable a `CONSOLE`, set a `MAIL_CHECK_ENAB` option to `no`, a `SU_WHEEL_ONLY` to `yes`, a `CRACKLIB_DICTPATH` to `/usr/lib/cracklib_dict`, a `LOGIN_RETRIES` to 3 and an `ENCRYPT_METHOD` to `SHA512`. Otherwise, remove a `CHFN_AUTH`, `CONSOLE`, `CRACKLIB_DICTPATH`, `ENV_HZ`, `ENVIRON_FILE`, `FAILLOG_ENAB`, `FTMP_FILE`, `LASTLOG_ENAB`, `MAIL_CHECK_ENAB`, `MOTD_FILE`, `NOLOGINS_FILE`, `OBSCURE_CHECKS_ENAB`, `PASS_ALWAYS_WARN`, `PASS_CHANGE_TRIES`, `PASS_MIN_LEN`, `PORTTIME_CHECKS_ENAB`, `QUOTAS_ENAB`, `SU_WHEEL_ONLY` options from `login.defs` configuration file, avoid installing manpages and pam.d files (`login`, `passwd` and `su`) that are provided by [sys-auth/pambase](../sys-auth/pambase.md).

Integrate with PAM infrastructure to perform authentication when doing a user or a group manipulation tasks.

This flag should be enabled if target system to be using a PAM stack for a user authentication.

### selinux
Pass the `--with-selinux` option to the configure script. Enable an ability to properly run under SELinux-restricted environment. A `useradd` and a `userdel` command will copy a security context from files when creating a user home directory from skeleton files or moving a home directory to the different place. Both of these commands also will support `-Z` option to add or remove SELinux user mapping for the user account. A `vipw` command will copy a SELinux context from original files to backup files. A `chsh` command will consult SELinux in order to check for permissions before changing a shell.

This flag should only be ever toggled system-wide, e.g. as part of SELinux-enabled Portage profile.

### skey
Pass the `--with-skey` option to the configure script. Provide an ability to authenticate using S/Key one-time password system.

It is safe to disable the flag.

### split-usr
When enabled, install the `passwd` command into the `/bin` directory and create a symlink pointing to it inside of the `/usr/bin` directory.

This flag should be enabled if the system uses separate `/usr` partition to ensure that the `passwd` command is available during the early boot.

### su
Pass the `--with-su` option to the configure script. Build and install the `su` binary, which allows to run a command with substitute user and group ID, and is designed mostly for unprivileged users.

This flag should normally be enabled, however it can be disabled if there is no need to run privileged commands as regular users or alternative mechanisms exist to run such commands.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### xattr
Pass the `--with-attr` option to the configure script. Provide an ability for a `useradd` and a `usermod` commands to copy eXtended ATTRibutes from source files into destination when creating a user home directory from skeleton files or moving home directory to different place. Enable an additional logic to exclude ACLs when copying XATTRs to avoid an unexpected permissions result while copying files between filesystems with and without an ACL support.

This flag should be toggled system-wide, otherwise there is a high chanse of losing XATTRs when using different tools.
