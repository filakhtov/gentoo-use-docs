# dev-perl/Net-HTTP

### minimal
The `Net::HTTP` module uses the `IO::Socket` module when available to handle low-level connections to the server and this flag pulls in one of the packages that provide this module. When disabled, this dependency wouldn't be pulled in and the `IO::Socket::INET` module, that only provides IPv4 functionality will be used.

This flag should be disabled if there is a need to use the `Net::HTTP` module for handling IPv6 connections.

### test
Execute the `make test` command from the source directory after the main build is completed to run the regression test suite provided with the source code. This will extend the build time.

This flag should normally be disabled, because it is mainly useful for the Gentoo team, testers and developers.
