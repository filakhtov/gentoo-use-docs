# dev-perl/Net-SSLeay

### examples
Install additional example files that show how to use the `Net::SSLeay` module for various use cases, including peer verification, sending data over an encrypted channel, contacting server using a client side certificate, setting ephemeral RSA key, etc into the `/usr/share/doc/Net-SSLeay-1.820.0/examples` directory.

It is safe to disable the flag.

### minimal
Only makes sense if the `test` flag is also enabled. Skip some of the dependencies required for extended test suites and execute only limited minimal regression tests.

This flag should normally be disabled.

### test
Execute the `make test` command when the main build is completed to run the test suite provided with the source code. This will extend a build time. Also, make sure that test and coverage files are removed from release before installation.

This flag should normally be disabled as these tests are mainly useful for the Gentoo team, testers or developers.
