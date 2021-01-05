# app-arch/tar

### acl
Pass the `--with-posix-acls` option to the configure script. Enable the `--acl` runtime option support. Allow `tar` to store ACL permissions while creating an archive and restore them when extracting one.

It is recommended to toggle this flag system-wide. Disabling this flag on the package while keeping it enabled in the system will result in losing ACL permissions while archiving and unarchiving.

### minimal
Remove all files except tar command itself before installing a package into the target system.

This flag should normally be disabled, otherwise only `tar` command will be available and not an `rmt`, a `backup-tar` or others.

### nls
Pass the `--enable-nls` option to the configure script. Provides localization via gettext library. For example, help and error messages translations will be available.

It is safe to disable the flag, unless there is a need for a non-English language.

### selinux
Pass the `--with-selinux` option to the configure script. Enable the `--selinux` runtime option support. Allow `tar` to backup and restore a SELinux context while archiving and unarchiving files.

This flag should be only ever toggled system-wide, e.g. as part of a SELinux enabled Portage profile.

### xattr
Pass the `--with-xattrs` option to the configure script. Enable the `--xattrs`, the `--xattrs-exclude` and the `--xattrs-include` runtime options support. Provide an ability to store xattr (eXtended ATTRibutes) in archive when creating one and restore them when extracting.
