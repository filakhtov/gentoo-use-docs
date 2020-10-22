# net-misc/rsync

### acl
Pass the `--enable-acl-support` option to the configure script. Enable a `-A` and a `--acls` runtime options to preserve ACLs while performing a file transfer.

It is recommended to toggle this flag system-wide, otherwise ACLs might be lost.

### examples
Install an example scripts into a `/usr/share/rsync` directory. This includes perl and shell scripts for various tasks, e.g. setting permissions and modification times, starting an unprivileged rsync daemon serving current directory, filter rsync daemon log messages and so on.

This flag can be safely disabled.

### iconv
Pass the `--enable-iconv` option to the configure script. Enable a runtime `--iconv` option to convert file names between different character sets during transfer.

It is safe to disable this flag.

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable IPv6 protocol support by rsync. When disabled, a `-6` and a `--ipv6` runtime options will be a no-op.

This flag should be enabled if the target system to be a part of an IPv6-capable network. Otherwise, it is safe to disable.

### libressl
Only works if the `ssl` flag is also enabled. Allow using the LibreSSH library instead of OpenSSL for cryptographic operations.

This flag should normally be disabled and only ever be toggled system-wide, because only one of the libraries can be installed on the same system at a time.

### lz4
Pass the `--enable-lz4` option to the configure script. Provide an ability to use the LZ4 compression algorithm when doing file transfer by passing the `--compress-choice=lz4` (or `--zc=lz4`) option to the `rsync` command.

It is safe to disable the flag.

### ssl
Pass the `--enable-openssl` option to the configure script. Install the `rsync-ssl` script that will use the `OpenSSL` to run an rsync copy to and from an rsync daemon that requires ssl connections (using the nginx or haproxy as an SSL-terminating proxy).

This flag should normally be disabled, unless there is an explicit need to connect to the rsync daemon over SSL.

### stunnel
Execute a `make install-ssl-client` and a `make install-ssl-daemon` commands during a build. Install a `rsync-ssl` and a `stunnel-rsync` scripts. Allow tunneling rsync traffic via TLS encrypted connection using stunnel.

This flag should normally be disabled, unless there is a need to encrypt rsync traffic using stunnel.

### system-zlib
Use the system zlib library instead of the one bundled with rsync sources for compression (see `--new-compress` and `--old-compress` options in man page). When this flag is disabled, pass the `--with-included-zlib` option to the configure script to use the bundled library.

This flag should normally be disabled, and the portage configuration needs to be changed to use `--new-compress` when this flag is enabled and there is a need to use compressed transfer for portage synchronization.

### xattr
Pass the `--enable-xattr-support` option to the configure script. Provide a `-X`, a `--xattrs` and a `--fake-super` runtime options for rsync. Enable an ability to preserve eXtended ATTRibutes during a file transfer.

It is recommended to toglle this flag system-wide, otherwise XATTRs might be lost.

### xxhash
Pass the `--enable-xxhash` option to the configure script. Provide support for xxHash checksum support - fast non-cryptographic hash algorithm, including newest XXH3 and XXH128 hashing routines to verify hashes during file comparison and transfer.

This flag should normally be enabled, as this feature is currently unstable and considered experimental.

### zstd
Pass the `--enable-zstd` option to the configure script. Provide an ability to use the zstd compression algorithm when doing file transfer by passing the `--compress-choice=zstd` (or `--zc=zstd`) option to the `rsync` command.

It is safe to disable the flag.
