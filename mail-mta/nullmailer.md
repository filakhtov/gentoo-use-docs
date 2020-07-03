# mail-mta/nullmailer

### ssl
Pass the `--enable-tls` option to the configure script. Use the `GnuTLS` library to provide TLS encryption capabilities, e.g. support for STARTTLS.

This flag should be enabled if there is a need for secure mail transport.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, as it is primarily oriented towards the developers, testers and maintainers.
