# virtual/perl-libnet

### ssl
Pull in the [dev-perl/IO-Socket-SSL](../dev-perl/IO-Socket-SSL.md) package as a dependency to enable SSL support in various modules provided by this package.

This flag can be safely disabled, however SSL support will be unavailable, e.g. `git send-email` won't be able to send emails using SSL-enabled servers.
