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

### static
Append a `-static` option to the `LDFLAGS` variable for the duration of a build. This will build and install statically linked `rsync` binary.

This flag should normally be disabled, unless there is an explicit need for a static binary.

### stunnel
Execute a `make install-ssl-client` and a `make install-ssl-daemon` commands during a build. Install a `rsync-ssl` and a `stunnel-rsync` scripts. Allow tunneling rsync traffic via TLS encrypted connection using stunnel.

This flag should normally be disabled, unless there is a need to encrypt rsync traffic using stunnel.

### xattr
Pass the `--enable-xattr-support` option to the configure script. Provide a `-X`, a `--xattrs` and a `--fake-super` runtime options for rsync. Enable an ability to preserve eXtended ATTRibutes during a file transfer.

It is recommended to toglle this flag system-wide, otherwise XATTRs might be lost.
