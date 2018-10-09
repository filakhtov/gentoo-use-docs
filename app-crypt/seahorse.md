# app-crypt/seahorse

### debug
Pass the `--enable-debug` option to the configure script. Disable compiler optimizations and build binaries and libraries with debugging symbols. Output additional debugging information at runtime, mainly around LDAP routines, e.g. dumping entries.

This flag should only be enabled for debugging purposes.

### ldap
Pull in the [net-nds/openldap](../net-nds/openldap.md) package as a dependency. Provide an ability to synchronize PGP keys with LDAP key server, to fetch fresh keys and publish any local key changes.

This flag should be enabled if there is a need to use LDAP based PGP keyservers with Seahorse.

### zeroconf
Pass the `--enable-sharing` option to the configure script. Use the Avahi client to discover shared PGP public keys over the DNS-SD (DNS Service Discovery) and HKP (HTTP Keyserver Protocol) protocols.

This flag should be enabled if there is a need to share or discover public PGP keys over the network.
