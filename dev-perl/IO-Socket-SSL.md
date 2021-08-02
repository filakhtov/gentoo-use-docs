# dev-perl/IO-Socket-SSL

### examples
Install additional example source code that shows how to use `IO::Socket::SSL` module to solve a number of different use cases, including example HTTPS server using nonblocking sockets and simple HTTP/HTTPS proxy into the `/usr/share/doc/IO-Socket-SSL-<VERSION>/examples` directory.

It is safe to disable the flag.

### idn
Pull in one of the packages that can provide an IDN (internationalized domain name) support to be able to establish a connection with hosts that have their domain names in non-Latin, language-specific script or alphabet.

This flag should be enabled if there is a need to handle domain names with non-Latin characters.

### test
Remove some unreliable test cases and execute the `make test` command from the source directory after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag should normally be disabled, because it is mainly useful for the maintainers, testers and developers.
