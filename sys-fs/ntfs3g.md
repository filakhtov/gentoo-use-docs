# sys-fs/ntfs3g

### acl
Pass the `--enable-posix-acls` option to the configure script. Enable support for POSIX ACLs (Access control list) to make it possible to grant access rights for reading, writing and executing to any designated user or group, usually using the `setfacl` and `getfacl` utilities.

This flag can be safely disabled, if there is no need to access or apply POSIX ACLs.

### debug
Pass the `--enable-debug` option to the configure script. Enable debugging code and additional log output. Enable the `-d` and `--debug` command line options support in various utilities (aka ntfsprogs) provided by this package.

The flag should normally be disabled, unless there is a need to perform debugging.

### external-fuse
Pass the `--with-fuse=external` (`internal` if the flag is disabled) option to the configure scrpit. Use an external (system) `libfuse` library, instead of embedded `fuse-lite` which is optimized for embedded Linux platforms.

This flag should normally be enabled, except for embedded systems.

### ntfsdecrypt
Pass the `--enable-crypto` option to the configure script. Build and install the `ntfsdecrypt` binary that allows to decrypt or update NTFS files encrypted according to EFS (Encrypting File System).

This can be safely disabled if there is no need to deal with NTFS EFS.

### ntfsprogs
Pass the `--enable-ntfsprogs` and `--enable-quarantined` options to the configure script. Build and install NTFS management utilities, including: `ntfsfix`, `ntfsinfo`, `ntfscluster`, `ntfsls`, `ntfscat`, `ntfscmp`, `mkntfs`, `ntfslabel`, `ntfsundelete`, `ntfsresize`, `ntfsclone`, `ntfscp`, `ntfswipe`, `ntfstruncate`, `ntfsrecover`, `ntfsusermap`, `ntfssecaudit`, `ntfsmftalloc`, `ntfsmove`, `ntfsck ntfsfallocate`, `mkntfs-attrdef`, `mkntfs-boot`, `mkntfs-sd`, `mkntfs-mkntfs`, `mkntfs-utils`,

This flag should normally be enabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libntfs-3g` library.

This flag should only ever be enabled if there is an explicit need for the static library.

### suid
Set the suid bit on the `ntfs3g` binary so that it can be executed by unprivileged users.

The flag should be enabled if there is a desire to allow regular users to use NTFS utils, however keep in mind that it might pose a security issue.

### xattr
Pass the `--enable-xattr-mappings` option to the configure script. Enable support for XATTRs (extended attributes) on NTFS filesystem (activated via the `streams_interface=xattr` mount option, which is enabled by default) and allow reading them using the `getfattr` and writing using the `setfattr` utilities.

This flag can be safely disabled, unless there is a need to use XATTRs on NTFS.
