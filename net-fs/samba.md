# net-fs/samba

### acl
Pass a `--with-acl-support` option to a WAF configure script. Enable support for extended access control lists (ACLs) and provide an ability to store them in Unix ACL XATTRs (eXtended ATTRibutes).

This flag should be enabled if there is a need to use extended ACLs.

### addc
No additional options are passed if the flag is enabled. When disabled, pass a `--without-ad-dc` option to a WAF configure script. Provide an ability for Samba to act as an AD DC (Active Directory Domain Controller).

This flag should only be enabled if there is a need to run a domain controller on top of Samba.

### ads
Pass a `--with-ads` option to a WAF configure script. Enable integration with ADS (Active Directory Services) using the Kerberos 5 and LDAP protocols and provide an ability to join as a member of an Active Directory domain.

This flag should only be enabled if there is a need to join an AD domain.

### ceph
Pass the `--enable-cephfs` option to the WAF configure script. Build and install the `vfs_ceph` VFS (Virtual File System) module to utilize features provided by the CephFS. Enable support for the `vfs objects` configuration option.

This flag should only be enabled if there is a need to expose shares that are located on CephFS volumes.

### client
Pull in the [net-fs/cifs-utils](../net-fs/cifs-utils.md) package as a dependency (and ensure that `ads` flag is enabled if necessary). CIFS utils provide an ability to access Windows or Samba file shares over an SMB (Server Message Block) protocol.

This flag should be enabled if there is a need to access file shares.

### cluster
Pass a `--with-cluster-support` option to a WAF configure script. Provide an HA (high-availability) load-sharing CIFS server cluster that:

- uses a CTDB (Clustered TDB) with automatic rebuild/recovery of the databases upon node failures,
- and supports node monitoring in the cluster and services running on each node,
- and manages a pool of public IP addresses that are used to provide services to clients.

This flag should only be enabled if there is a need to run HA cluster.

### cups
Pass a `--enable-cups` option to a WAF configure script. Enable support for CUPS (Common Unix Printing System) based printers and print jobs, to allow them to be shared with or managed by other systems over an SMB (Server Message Block) protocol.

This flag should be enabled if there is a need to share local CUPS printers over an SMB protocol.

### debug
Pass the `--with-lttng` option to the WAF configure script. Use the LTTng (Linux Trace Toolkit Next Generation) framework to enable tracing in order to analyze behavior and interaction between various components of Samba and operating system.

This flag should only be enabled for debugging purposes.

### dmapi
Pass a `--with-dmapi` option to a WAF configure script. Enable support for a Data Management API (DMAPI) interface for Hierarchical Storage Management (HSM) for an XFS filesystem.

This flag should only be enabled if there is a need to run samba on an XFS filesystem.

### fam
Pass a `--with-fam` option to a WAF configure script. Build a `vfs_notify_fam` - VFS (virtual file-system) Samba module that makes use of the system FAM (File Alteration Monitor) daemon to implement file change notifications for Windows clients. FAM is generally present only on IRIX and some BSD systems.

This flag should only be enabled if the target systems supports FAM and there is a need to support client notification.

### glusterfs
Pass the `--enable-glusterfs` option to the WAF configure script. Build and install the `vfs_glusterfs` VFS (Virtual File-System) module provides an alternative, and superior way to access a Gluster filesystem from Samba for sharing. It does not require a Gluster FUSE mount but directly accesses the GlusterFS daemon through its library libgfapi, thereby omitting the expensive kernel-userspace context switches and taking advantage of some of the more advanced features of GlusterFS.

This flag should only be enabled if there is a need to use GlusterFS for Samba shares.

### gpg
Pass a `--with-gpgme` option to a WAF configure script. Provide an ability to store cleartext passwords in a PGP/OpenGPG encrypted form by configuring the new "password hash gpg key ids" option.

This flag should only be enabled if there is a need to use PGP-encrypted passwords.

### iprint
This flag only works if the `cups` flag is enabled. Pass a `--enable-iprint` option to the WAF configure script. Use iPrint server libraries from Novell to provide an ability to share printers provided by such a server with other systems using an SMB (Server Message Block) protocol.

This flag should only be enabled if there is a need to use printers provided by Novell iPrint printing server.

### json
Pass the `--with-json` option to the WAF configure script. Use the `libjansson` library to enable support for JSON (JavaScript Object Notation) format, required for using samba in AD DC mode (Active Directory Domain Controller). Also provide an ability to generate audit logs in JSON format.

It is safe to disable the flag.

### ldap
Pass a `--with-ldap` option to a WAF configure script. Provide an ability to use a LDAP directory to provide an authentication layer in addition to containing the user, group, and machine account information. Build and install various `smbldap-*` utilities, e.g. `smbldap-groupadd`, `smbldap-useradd`, `smbldap-passwd`, `smbldap-userinfo` and others.

This flag should only be enabled if integration with LDAP is desired.

### pam
Pass a `--with-pam` and a `--with-pammodulesdir=/lib/security` options to a WAF configure script. Build and install a `pam_winbind` module to integrate Samba with a PAM (Pluggable Authentication Modules) infrastructure. This module can authenticate users against the local domain by talking to the Winbind daemon.

This flag should only be enabled if there is a need to integrate with the PAM subsystem.

### profiling-data
Pass the `--with-profiling-data` option to the WAF configure script. Enable support for collection of profile information during runtime. The number of calls to and the amount of time spent in various system calls, smb transactions and nmbd activity can be recorded.

It is recommended to disable this flag, as it is mainly useful for Samba developers.

### python
Build and install a wide variety of Python-based Samba tools, libraries and modules, e.g. `smbtorture` - a testsuite for finding differences in implementations of the SMB protocol and testing SMB servers, `pytalloc-util` - utility functions library for using talloc objects with Python, `pytevent` - Python bindings for tevent and many others. A lot of these tools are required for AD DC (Active Directory Domain controller). When disabled, apply a set of patches that provide an ability to disable Python bindings and pass the `--disable-python` option to the WAF configure script to do so.

This flag can be safely disabled if Python tools aren't necessary and must be enabled if AD DC is necessary.

### quota
Pass a `--with-quotas` option to a WAF configure script. Enable support for filesystem disk quotas and provide an ability to limit disk space usage for file shares.

This flag should only be enabled if there is a need to use disk quotas.

### regedit
Pass the `--with-regedit` option to the WAF configure script. Build and install the `samba-regedit` - an ncurses based tool to manage the Samba registry and can be used to show and edit registry keys, subkeys and their values.

It is safe to disable this flag.

### selinux
Pull in a [sec-policy/selinux-samba](../sec-policy/selinux-samba.md) package as a dependency that provides SELinux policies required for a proper Samba operation under a SELinux restricted kernel.

This flag should only be ever toggled system-wide, i.e. as part of a SELinux-enabled portage profile.

### snapper
Pass the `--enable-snapper` option to the WAF configure script. Build and install the `vfs_snapper` VFS module that exposes snapshots managed by snapper (snapshot tool) for use by Samba. This provides the ability for remote SMB clients to access shadow-copies via Windows Explorer using the "previous versions" dialog.

It is safe to disable this flag.

### spotlight
Pass the `--with-spotlight` option to the WAF configure script. Enable support for macOS Spotlight support, i.e. provide an ability to index files located on a Samba share server-side in the Elasticsearch or Gnome Tracker backend and expose a way for clients to search through the indexed data.

This flag should only be enabled if there is a need to serve macOS clients that use Spotlight.

### syslog
Pass a `--with-syslog` option to a WAF configure script. Allow to send Samba messages to a Unix system logger instead of or in addition to standard Samba logging file. Provide support for a `syslog` configuration option to control log level sent to syslog.

This flag should only be enabled if there is a need to use syslog for logging.

### system-heimdal
Pull in a [app-crypt/heimdal](../app-crypt/heimdal.md) package as a dependency. Use Heimdal implementation of the Kerberos 5 authentication protocol provided by the package in order to integrate with Active Directory.

This flag should only be enabled if there is a need to use Heimdal implementation to handle AD authentication.

### system-mitkrb5
Pass a `--with-system-mitkrb5` option to the WAF configure script. Pull in a [app-crypt/mit-krb5](../app-crypt/mit-krb5.md) package as a dependency. Use MIT implementation of the Kerberos 5 authentication protocol provided by the package in order to integrate with Active Directory.

This flag should only be enabled if there is a need to use MIT implementation to handle AD authentication.

### systemd
Pass a `--with-system` option to a WAF configure script. Enable integration with a SystemD init system, e.g. notifying it when forking and ready to serve connections via `sd_notify`. Also provide better logging integration with journald backend.

It is recommended to toggle this flag system-wide, e.g. as part of a SystemD Portage profile.

### test
Pass a `--enable-selftest` option to a WAF configure script. Execute a `waf test` command after a main build is completed to run a test suite provided with a source code. The test suite is broken and does not run properly as part of the emerge.

This flag should be disabled, as it will fail a build.

### winbind
Pass a `--with-winbind` option to a WAF configure script. Build and install a `winbindd` daemon that provides an ability to deploy a Samba server with no preexisting Unix account infrastructure, i.e. the Winbind acts as an intermediary between Unix services and Windows domain controllers, offers a means to manage domain users and groups without the overhead of local accounts.

This flag should be enabled if there is a need for Winbind daemon or libraries.

### zeroconf
Pass a `--enable-avahi` option to a WAF configure script. Use an Avahi service discovery suite to advertise available Samba shares via a mDNS (Multicast DNS) protocol so that they can be automatically discovered by other hosts, in particular macOS.

This flag should only be enabled if there is a need to advertise shares via the mDNS.
