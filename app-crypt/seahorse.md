# app-crypt/seahorse

### ldap
Pull in the [net-nds/openldap](../net-nds/openldap.md) package as a dependency. Pass the `-Dldap-support=true` (`false` if the flag is disabled) option to the meson build command. Provide an ability to synchronize PGP keys with LDAP key server, to fetch fresh keys and publish any local key changes.

This flag should be enabled if there is a need to use LDAP based PGP keyservers with Seahorse.

### zeroconf
Pass the `-Dkey-sharing=true` (`false` when the flag is disabled) option to the meson build command. Use the Avahi client to discover shared PGP public keys over the DNS-SD (DNS Service Discovery) and HKP (HTTP Keyserver Protocol) protocols.

This flag should be enabled if there is a need to share or discover public PGP keys over the network.
